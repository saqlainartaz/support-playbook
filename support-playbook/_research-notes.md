# Research Notes (internal — distilled from Intercom)

**Support teammate:** admin id `9050625`, name "Support", email `support@insidesuccesstv.com`
(from-name "Support from Inside Success", sends via support@mawercapital.com).
Only this teammate's `comment` parts are documented. Fin bot ("Inside Success AI", id 9050629)
and other admins (e.g. Luke Gent, id 9091191) are excluded.

Window: conversations created on/after 2026-03-15 (last 3 months). Source: closed convs where
teammate 9050625 participated (100 in window, page 1).

PII stripped from all examples below.

---

## Billing & Payments

### Case: "When is my next payment / which card?" (215474666712540)
Customer: moving along gathering videos, asks when next payment is due and whether it'll hit
the original card or a different one.
**Support reply (verbatim, anonymized):**
> Hi {FirstName},
> Thanks for checking in. Your payment will auto-renew on {date}, and it'll be charged to the
> card on file ending in {last4}.
> If you'd prefer to use a different card, just let me know, and I'll send over a secure link
> to update it before then.
> Best,

Pattern: confirm renewal date + card last4, offer secure link to change card. Warm, concise.

### Case: Outbound "Payment Issue – How Can We Assist?" (failed recurring payment) — TEMPLATE (215474646935274)
This is an admin_initiated email authored BY Support (id 9050625). Reusable outreach template:
> Hey!
> I hope this email finds you well! I'm writing to let you know that your most recent recurring
> payment for our services was unsuccessful.
> Please don't worry – these things happen! Could you let us know how you'd like to handle this?
> If you need to update your credit card info or use a different card than the one we have on
> file, it's super easy!
> You can update your credit card info with this link: {secure card-update link}
> This form only collects info and does not charge your card. Once you're done, let me know so
> I can apply the new info to your account.
> If you have already spoken to a team member about your payment, please let me know in your
> reply so I can update our systems to reflect this.
> I look forward to your response today.
> Best regards,

### Case: Payment hardship / deferral request (215474646935274 reply)
Customer: personal hardship, will pay later this month and double up next month.
**Support reply (anonymized):**
> Hi {FirstName},
> Thanks for the update, and sorry to hear about {the challenges you're facing}. That plan
> works. Make this month's payment when you can, and double up on the next one after you're
> back on {date}. I'll note your account, so nothing further goes out in the meantime.
> I've also passed your note along to the {script} team - someone will be in touch with you
> directly about {topic}.
> Just let me know when you're ready to make the payment I will send you the new link.
> Best,

Pattern: empathize → accept the deferral plan → reassure "I'll note your account, nothing
goes out in the meantime" → route any production notes to the right team → offer payment link
when ready.

---

## Pre-Shoot Coordination

### Case: Reschedule / move / cancel a studio session (215474701133137)
Customer: scheduled a studio session, needs to push/cancel it (accident, can't travel) and
rebook later. (Topic: Pre-Shoot Coordination, tag "pre shoot".)
**Support reply (anonymized):**
> Hi {FirstName},
> Sorry to hear that, you can use this link to reschedule your session
> {OnceHub reschedule link — https://go.oncehub.com/inside-success?...}
> Thank you
> {Agent name}
> Client Concierge Manager

Pattern: brief empathy → self-serve reschedule link (OnceHub `go.oncehub.com/inside-success`)
→ signed by the concierge. Same link/flow covers reschedule, move-ahead, and cancel-then-rebook.
Note: replies are signed with a real agent name (e.g. "Angelina, Client Concierge Manager") or
just "Best,". The Support inbox is staffed by named concierges.

---

## Episode Review & Approval

### Case: Outbound "Your Episode Is Ready for Approval" — TEMPLATE (215474641408747)
Automated email authored by Support (id 9050625). Reusable template:
> Hi {FirstName},
> Thank you again for your incredible work on this project. Your episode is now ready for final
> approval.
> We've implemented your edits and ensured this version reflects your vision as closely as possible.
> As a reminder, the 7-day editing window from the original delivery has now passed. At this
> stage, we need to move forward with approval and publishing.
> Please review your episode here: 👉 {episode review link}
> Please sign here so we can proceed with publishing: https://www.insidesuccesstv.com/episodeapproval
> Once approved, we'll finalize and notify you as soon as your episode is live.
> Warm regards,

### Case: "I can't sign off / approval link won't work" (215474641408747 reply)
Customer: "it's awesome! but it's not allowing me to sign off" (+ screenshot).
**Support reply (anonymized):**
> Hi {FirstName},
> The link is accessible, you may need to change your browser or try a different device
> https://www.insidesuccesstv.com/episodeapproval
> Thanks
> {Agent name}
> Client Concierge Manager

Pattern: reassure the link works → suggest different browser/device → re-share approval URL.
Key fact: approval is done at `insidesuccesstv.com/episodeapproval`; there is a 7-day editing
window from original delivery, after which they move to approval/publishing.

---

## B-Roll / Footage Submission

### Case: "How do I submit B-roll? What's acceptable?" (215474655526394)
Customer asks: can I use Pixieset? can footage be shot on iPhone? can I submit an external
TV-news interview clip? (Topic: B-Roll Submission, tag B-ROLL.)
**Support reply (human, anonymized):**
> Hi {FirstName},
> Thank you!
> We only accept b Roll material on google drive or dropbox, please ask the videographer to
> transfer everything onto one of those platforms and then share the link to the folder to this
> support email.
> They interviews can be done on an iphone, they must be filmed horizontal
> You can submit the footage from the new station-congrats!
> Thank you
> {Agent name}
> Client Concierge Manager

Key facts (also confirmed by Fin's article-cited answer in same thread):
- **Accepted submission method:** Google Drive or Dropbox folder link only, shared to the
  support email; set folder permissions to "Anyone with the link can view."
- iPhone footage is fine if clear/well-lit; **must be filmed horizontal**.
- External/news footage is OK if relevant; label files + include timestamps for specific moments.
- Keep clips short (~10–60s), organized/labeled; avoid hours of unlabeled footage.
- **Related Help Center articles:** "B-roll and photo submission guide"
  (intercom.help/inside-success/en/articles/15327020-...), "Pre-shoot checklist and updates
  before your shoot" (.../15331170-...).

---

## Money Mondays / Calls

### Case: "Can't join the Monday marketing call / need the link" (215474712437644)
Customer: trying to join Monday marketing calls, gets "DNS points to prohibited IP" error on
iPhone, asks for a working link. (tag "money mondays".)
**Support reply (human, anonymized):**
> Hi {FirstName},
> The zoom meeting works, here is the link {Money Monday Zoom link}
> You may have to change browser settings if you can't access the link
> Thank you
> {Agent name}
> Client Concierge Manager

Durable facts (from human reply + Fin's article-cited answer in same thread):
- **Money Monday goes live every Monday at 11:30 a.m. EST.**
- Public join link: https://www.insidesuccesstv.com/mondaylive (redirects to the Zoom room).
- Troubleshooting connection/DNS errors: try a different browser (Safari vs Chrome), switch
  network (Wi-Fi ↔ cellular), or adjust browser settings.
- **Related Help Center article:** "Marketing and Promotion Intensive and event participation"
  (intercom.help/inside-success/en/articles/15331495-...).

---

## Casting Inquiries

### Case: Casting-call prep / timeline confusion (215474668856824)
Customer replied to the "How to Prepare For Your Casting Call" email, confused about the
cohort cut-off date vs. their scheduled call. (tags: casting, pre shoot.)
**Support reply (human, anonymized):**
> Hi everyone,
> I am not in the casting dept. but I asked a member of the team to confirm the cut off date.
> Thank you
> {Agent name}
> Client Concierge Manager

Pattern (IMPORTANT cross-cutting behavior): when the question is outside Support's lane
(casting decisions, scripting, production specifics), Support does NOT guess — they loop in the
relevant internal team and tell the customer they've done so. The key reassurance Fin/Support
gives on timeline: **decision timing is based on the date of YOUR individual casting call**, not
a generic cohort date.

Durable casting facts (from the outbound "How to Prepare" prep email — useful reference):
- The casting call IS the official audition. Two evaluation criteria: (1) Alignment of brand/
  story/message with the audience; (2) "Green Light" — if approved on the call, a social
  media/Google background check runs and the external team emails by ~10am EST next day to
  confirm casting.
- Current cohort closes Sunday 11:59pm; if accepted, a second call covers onboarding/scripting
  and a date to fly to Miami within 2026.
- Prep steps: review the info page, study the studio mission/current cast, watch ≥1 episode
  (CEO's episode recommended), be professional on camera (not in a car, good video/lighting).
- Studio address: 1210 Washington Ave, Unit 250, Miami, FL 33139.
- **Related Help Center article:** "How casting works"
  (intercom.help/inside-success/en/articles/15346706-...).
- Note: the Support inbox also sends from `inside@insidesuccesstv.com` in some threads.

---

## Assets & Documents

### Case: "Can I get a copy of the original contract / an asset?" (215474654565058)
Customer (a client's assistant) requests a copy of the original signed contract ahead of a
shoot. (Topic: Asset Request, tag Assets.)
**Support reply (human, anonymized):**
> Hi {FirstName},
> Attached is the contract!
> Thanks
> {Agent name}
> Client Concierge Manager

Pattern: document/asset requests (contract copies, agreements, deliverables) → Support locates
and attaches the file directly, CC'ing the relevant internal owner (e.g. the account/legal
contact) on the reply. Fast, friendly, no friction.

---

## Cross-cutting voice & tools (applies to every category)
- **Voice:** warm, brief, first-name greeting, plain language, often signed
  "{Agent}, Client Concierge Manager" or just "Best,". Empathize first on negative-sentiment
  emails.
- **Stay in lane:** if a question belongs to another dept (casting decisions, scripting,
  production), loop in that team and tell the customer — don't guess.
- **Self-serve links Support reuses:**
  - Reschedule/booking: OnceHub `go.oncehub.com/inside-success`
  - Update card / failed payment: secure card-update link (whop checkout link)
  - Episode approval/sign-off: `insidesuccesstv.com/episodeapproval`
  - Money Monday live call: `insidesuccesstv.com/mondaylive` (Mondays 11:30am EST)
  - B-roll submission: Google Drive or Dropbox folder link (view access) to the support inbox
- **Help Center articles to cite:** B-roll & photo submission guide; Pre-shoot checklist;
  How casting works; Marketing/Promotion Intensive & event participation.
- **Common tech fix:** "link won't open" → try a different browser or device, or switch
  Wi-Fi ↔ cellular.

---

## (Billing) Note on disputes/chargebacks
A dispute thread (215474700471235, "I'll call Amex and block this charge") was handled by a
DIFFERENT teammate (Luke Gent), so it is excluded from the Support playbook. If a Support-authored
dispute reply surfaces, add it here.
