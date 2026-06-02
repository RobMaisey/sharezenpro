# DECISIONS — sharezenpro

- **Repo:** RobMaisey/sharezenpro
- **Domain:** sharezenpro.com (apex) — live at https://sharezenpro.com (HTTP 200, valid HTTPS)
- **Host:** GitHub Pages (build from `main`, root). CNAME file = `sharezenpro.com`.
- **Files:** index.html, start.html, privacy.html, terms.html, styles.css, CNAME, README.md.

Follows the migration/decision-log pattern (template: `sharezen-hub`).
**First entry: pre-fix AUDIT — 2026-06-01. Report only; nothing changed. Fixes to be
approved one at a time before any edit.**

---

## AUDIT — by area

### 1. Internal links — PASS
- `index.html` → `start.html`, `privacy.html`, `terms.html`: all exist and resolve.
- index nav anchors `#how`, `#why`, `#features`, `#pricing`: all match real section IDs.
- `start.html`, `privacy.html`, `terms.html` are REAL, full pages — not stubs.

### 2. Old `www.sharezen.com` links — NEEDS FIX (3 found; live-checked 2026-06-01)
- **index.html footer**, "ShareZen Group" → `https://www.sharezen.com/`
  (301 → https://sharezen.com/). Works via redirect, but points at the old www. Should be the
  canonical **https://sharezen.com**.
- **privacy.html §6**, "deleting your account" → `https://www.sharezen.com/deleting-your-account.html`
  → resolves to a **404** on the new hub. BROKEN.
- **terms.html §9**, "account deletion" → same URL → **404**. BROKEN.
- Decision needed for the two account-deletion links: the old Weebly page is gone. Options:
  point to a real deletion flow (e.g. inside app.sharezen.com), create a deletion page, or
  reword to describe the process. (Not just a www→non-www swap — the target page does not exist.)

### 3. start.html — what it actually does
- It is a marketing/landing page, **not** a form. No signup form lives on it.
- Every "Start free trial" button site-wide links to `start.html`.
- On start.html the real action is **"Create your free account" → https://app.sharezen.com/users/new**
  (the live platform's real signup). "Log in" → https://app.sharezen.com/user_session/new.
- Trial path: button → start.html → app.sharezen.com/users/new (real account creation).
  Not a placeholder. `app.sharezen.com` is the separate software platform (left untouched).

### 4. Technical basics — PASS
- All four pages have their own `<title>`, meta `description`, `viewport` tag, and an inline
  SVG favicon. privacy/terms also set `robots=noindex` (sensible for legal pages).
- No separate `favicon.ico` file, but the inline SVG favicon is valid and present everywhere.

### 5. Consistency — header/footer differ by page (confirm intended)
- Shared `styles.css`, fonts, palette across all pages. ✓
- **Header:** full nav menu (How it works / Why share / Features / Pricing) appears ONLY on
  index.html. privacy/terms use a reduced header (brand + Log in + Start free trial, no menu).
  start.html shows only brand + Log in.
- **Footer:**
  - index.html: full footer (brand blurb, Product column, Company column with phone/email +
    "ShareZen Group" link, bottom bar with Terms/Privacy).
  - privacy.html & terms.html: minimal footer (bottom bar only — copyright + Terms/Privacy/Home).
  - **start.html: NO footer at all.**
- **Contact details** ((604) 904-9400, rob@sharezen.com): present on index (footer),
  privacy (§11), terms (§11); **absent on start.html**.
- Likely deliberate conversion-page minimalism, but flagged for confirmation.

### 6. Placeholder / unfinished content — NEEDS ATTENTION before any launch push
- **index testimonials:** SAMPLE quotes. Visible "Sample quote" labels; on-page note
  "Placeholder quotes shown — swap in real testimonials ... with permission" + HTML comment
  "replace ... before launch." Needs real, permissioned quotes (or remove the section).
- **index product mockups** (calendar/ledger): illustrative, with on-page note "Illustrative
  of the ShareZen interface — swap in real app screenshots before launch."
- **privacy.html:** labelled "Template — not legal advice ... starting draft." Needs
  professional/legal review (PIPEDA / BC PIPA).
- **terms.html:** labelled "Template — not legal advice ... starting draft." Needs lawyer review.
- No lorem ipsum, "TODO", or "coming soon" text found.

### Minor / brand notes
- privacy.html & terms.html call the product "ShareZen Organizer Pro"; the rest of the site
  says "ShareZen". Legacy name — confirm the preferred product name.
- index footer: "A division of Sharezen Consulting Ltd."; legal pages: "operated by Sharezen
  Consulting Ltd." Minor wording difference.

---

## GAP LIST (for joint decision — NOTHING changed yet)
1. index footer "ShareZen Group" link → change `https://www.sharezen.com/` to `https://sharezen.com`.
2. privacy.html + terms.html account-deletion links → currently 404; decide the correct target.
3. start.html → no footer / no contact details: confirm intended, or add a minimal footer.
4. index testimonials → replace sample quotes with real permissioned ones, or remove.
5. index mockups → replace with real screenshots before launch (or keep as labelled illustration).
6. privacy.html + terms.html → template drafts; get professional/legal review.
7. (Minor) product-name consistency: "ShareZen Organizer Pro" vs "ShareZen".

_Guardrails: no DNS changes; app.sharezen.com untouched; other repos untouched; nothing
deleted; no push without approval._

---

## Changes applied — 2026-06-01
Four commits pushed to origin/main (live on sharezenpro.com):
- `4507085` — index.html footer "ShareZen Group" link changed to https://sharezen.com (was old
  www); product name standardised "ShareZen Organizer Pro" -> "ShareZen" in privacy.html and
  terms.html. (Also added this DECISIONS.md.)
- `5e0372a` — privacy.html §6: deletion sentence reworded to in-app deletion; removed the broken
  https://www.sharezen.com/deleting-your-account.html link.
- `100cf91` — terms.html §9: same fix (in-app deletion; broken link removed).
- `b219c07` — index.html: removed the placeholder testimonials section (sample quotes) and the
  "Illustrative ... swap in real app screenshots before launch" mockup note (mock images kept).

Deliberately NOT changed: terms §4 cancellation/refund wording; payment wording kept generic
(payment processor not named).

Still open from the audit gap list: start.html footer/contact (gap 3); real testimonials if
wanted later (gap 4); real mockup screenshots (gap 5); professional/legal review of the
privacy & terms template text (gap 6).
