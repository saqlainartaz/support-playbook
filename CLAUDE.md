# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A support-response **playbook** for Inside Success TV's Client Concierge team, distilled from
real Intercom support emails. It exists in two forms that mirror the same content:

- **Markdown source** — `support-playbook/README.md` + seven category files (the human-editable reference).
- **Web app** — `support-playbook/index.html`, a single self-contained page (search, category
  filters, one-click "copy reply") that the team actually uses day to day.

There is no build system, package manager, framework, or test suite — it's static markdown plus
one HTML file. It is deployable on Vercel as a pure static site via a root `vercel.json` (still
no build step, package manager, or framework — see **Deploy** below). (Note: `~/Documents/CLAUDE.md`
is a separate, workspace-level Trigger.dev automation guide and does **not** govern this static
project — ignore it here.)

## Run / preview

- Just open `support-playbook/index.html` in a browser (double-click works).
- Local server — matches `.claude/launch.json` (config name `playbook`):
  `python -m http.server 4173 --directory support-playbook` → http://localhost:4173
  A server is mainly needed so the logo (`images.jpeg`) loads; the page otherwise runs from `file://`.
- Keyboard: `/` focuses the search box from anywhere; `Esc` (while focused) clears it.

## Deploy (Vercel)

The root `vercel.json` makes the repo deploy as a static site with the playbook served at the
**domain root**. It rewrites `/` → `/support-playbook/index.html` and catches all other paths
(`/(.*)` → `/support-playbook/$1`) so the relative `images.jpeg` resolves without changing the
HTML. No build step is involved.

- **Git:** connect the repo in Vercel, accept the defaults (Framework: Other, no build command,
  Root Directory `.`), and deploy. Pushes to the connected branch auto-publish.
- **CLI:** `npx vercel` from the repo root for a preview, then `npx vercel --prod` to promote.
- Editing `vercel.json` doesn't affect local use — double-clicking `index.html` (`file://`)
  ignores it.

## ⚠️ Two sources of truth — keep them in sync

The app does **not** read the markdown files. `index.html` embeds all content in a `DATA`
JavaScript array near the bottom of the file. **Editing any reply, scenario, or category means
updating BOTH** the relevant `support-playbook/*.md` file AND the matching object in `DATA`
inside `index.html`. The seven categories map 1:1:

| Markdown file | `DATA` id |
|---|---|
| `billing-and-payments.md` | `billing` |
| `pre-shoot-coordination.md` | `pre-shoot` |
| `b-roll-and-footage-submission.md` | `b-roll` |
| `episode-review-and-approval.md` | `episode` |
| `assets-and-documents.md` | `assets` |
| `casting-inquiries.md` | `casting` |
| `money-mondays-and-calls.md` | `calls` |

Each `DATA` entry is a category object `{ id, name, desc, icon, cases[] }` — `icon` is an inline
SVG string and `desc` is the subtitle shown under the category. Each case object is
`{ title, keywords, says, steps[], reply, watch[], na?, ref? }`. `keywords` powers search and is
**not** shown in the UI — add search terms there to make a case findable. `reply` is the
copy-to-clipboard text; use `null` + `na` for cases with no canned reply. `ref` is an optional
`{ title, items[] }` block rendered as a highlighted reference panel instead of the "Watch out for"
list. Adding a new category means adding a 1:1 markdown file *and* a matching `DATA` entry (id +
icon) — the category map below stays in lockstep.

## index.html architecture

- Fully self-contained (inline CSS + JS + content). The only external dependencies are Google
  Fonts (Bricolage Grotesque + Hanken Grotesk; degrade to system fonts offline) and the logo
  `images.jpeg` — keep `images.jpeg` next to `index.html` when moving or hosting.
- **Theming:** CSS custom properties under `[data-theme="dark"]` and `[data-theme="light"]`
  (**light** is the first-visit default — set on `<html>` and in `initTheme()`). The toggle
  persists to `localStorage` key `pb-theme`; a stored preference always wins. The accent is the
  logo's **gold** (`#dcb56b` on dark,
  the darker `#8a6417` on light for WCAG-AA contrast). Add colors as tokens — don't hardcode.
- Rendering is plain DOM building from `DATA` (no framework): `render()` rebuilds sections,
  `cardEl()` builds each card, search filters `DATA` live, category pills filter/scroll.
- The logo sits in a dark "lockup" and is cropped with `object-fit:cover` because the source
  `images.jpeg` is a square with heavy black padding.

## Content rules (provenance)

- Replies are grounded in **real Support-team emails** — do not invent policy or templates. Use
  `[brackets]` for anything customer-specific, and never include customer PII.
- Scope is the Intercom **"Support" teammate** (admin id `9050625`, `support@insidesuccesstv.com`),
  distinct from the Fin AI bot and other admins. Pull source data via the Intercom MCP tools:
  `search_conversations` with `teammate_ids: ["9050625"]`, then `get_conversation`.
- `support-playbook/_research-notes.md` is an internal log mapping each template to its source
  Intercom conversation ID — update it when adding or refreshing cases. It is not part of the
  published playbook.
