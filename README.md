# Support Playbook

A support-response **playbook** for Inside Success TV's Client Concierge team — distilled from
real support conversations into ready-to-send reply templates, organized by situation.

It ships in two mirrored forms:

- **Web app** — [`support-playbook/index.html`](support-playbook/index.html): a single
  self-contained page with live search, category filters, and a one-click **Copy reply** button.
  This is what the team uses day to day.
- **Markdown source** — [`support-playbook/README.md`](support-playbook/README.md) plus seven
  category files (the human-editable reference).

There's no build system, package manager, or framework — it's static markdown plus one HTML file.

## Run locally

- **Easiest:** double-click [`support-playbook/index.html`](support-playbook/index.html) to open
  it in your browser.
- **Local server** (needed only so the logo loads reliably):
  ```bash
  python -m http.server 4173 --directory support-playbook
  # → http://localhost:4173
  ```

Keyboard: `/` focuses search from anywhere; `Esc` clears it.

## Deploy (Vercel)

The repo deploys as a static site via the root [`vercel.json`](vercel.json), which serves the
playbook at the domain root (no build step).

- **Git:** import this repo in Vercel and accept the defaults (Framework: Other, no build command,
  Root Directory `.`). Pushes to `main` auto-publish.
- **CLI:** `npx vercel` for a preview, then `npx vercel --prod` to promote.

## Structure

```
support-playbook/
  index.html        ← the web app (search + copy-reply)
  README.md         ← team-facing guide
  *.md              ← seven category source files
  images.jpeg       ← logo (keep next to index.html)
vercel.json         ← static-deploy config
CLAUDE.md           ← guidance for working in this repo
```

## ⚠️ Two sources of truth

The app does **not** read the markdown files — `index.html` embeds all content in a `DATA` array
near the bottom of the file. **Editing any reply, scenario, or category means updating BOTH** the
relevant `support-playbook/*.md` file AND the matching object in `DATA`. See
[`CLAUDE.md`](CLAUDE.md) for the full category-to-`DATA` mapping and content rules (replies are
grounded in real support emails — don't invent policy, and never include customer PII).
