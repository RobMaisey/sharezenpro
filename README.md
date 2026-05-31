ShareZen — Sharing website
Static marketing site for **ShareZen Organizer Pro (the sharing software)**, hosted on GitHub Pages.
No build step, no dependencies — edit the files and commit.
> **Source of truth:** the full operational details (domains, DNS, accounts, brand,
> migration plan) live in the private **`SHAREZEN-WEBSITES.md`** master control file
> (private repo + Google Drive → ShareZen). Read that first when picking this up.
Files
File	Purpose
`index.html`	The page(s).
`styles.css`	Shared design system (Fraunces + Hanken Grotesk; "cabin / golden hour" theme).
`CNAME`	Binds the repo to its custom domain.
Deploy / update
First deploy: upload files (incl. `CNAME`) → Settings → Pages → Deploy from branch `main` / root → tick Enforce HTTPS once DNS resolves.
Edit text: open a file → ✏️ pencil → edit → Commit. Live in ~1 minute.
Bigger change: upload the updated file (overwrites) → Commit.
DNS (custom domain → GitHub Pages)
Four `A` records on `@` → `185.199.108.153–111.153`, and a `CNAME` `www` → `robmaisey.github.io`.
Leave any `_acme-challenge` TXT records (GitHub adds them for HTTPS).
Don't forget
Brand, positioning, and taglines: see the master control file.
This README is public — no accounts, passwords, or private notes here.
