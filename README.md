# ShareZen Sharing — Landing Site

A fast, self-contained static marketing site for **ShareZen Organizer Pro**, built to convert visitors to a 30-day free trial ($19/month, cancel anytime). No build step, no dependencies, no external images — ready for GitHub Pages.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The landing page (hero → problem → model → why-share-not-rent → product mockups → use cases → testimonials → pricing → FAQ → CTA). |
| `start.html` | The dedicated conversion page. All "Start free trial" buttons lead here; its single CTA opens the app sign-up. |
| `terms.html` | Terms of Service (template — review with a lawyer). |
| `privacy.html` | Privacy Policy (template — review with a lawyer). |
| `styles.css` | The full design system (warm editorial "cabin / golden hour" theme). |

**Conversion funnel:** Landing → `start.html` ($19/mo · cancel anytime) → `app.sharezen.com/users/new`.

## Deploy to GitHub Pages

1. Create a new repository (e.g. `share-your-toys`).
2. Upload `index.html`, `start.html`, and `styles.css` to the repository root.
3. Go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then **Save**.
6. Your site goes live at `https://<username>.github.io/<repo>/` within a minute or two.

### Use a custom domain (recommended)
On the same **Pages** screen, add your domain (e.g. `shareyourtoys.com`) under **Custom domain**, then point your DNS:
- A CNAME record from `www` to `<username>.github.io`, **or**
- Four `A` records for the apex domain to GitHub's IPs (`185.199.108–111.153`).

A `*.weebly.com` or `*.github.io` subdomain works for launch, but a real domain converts better and looks more trustworthy.

## Things to customize before launch

- **App links** — currently point to `app.sharezen.com/users/new` (sign-up) and `app.sharezen.com/user_session/new` (login). Update if those routes change.
- **Brand name** — the site uses "ShareZen." If you adopt "Share Your Toys" as the consumer brand, update the `.brand` text in both HTML files.
- **Contact** — phone `(604) 904-9400` and `rob@sharezen.com` are in the footer; swap for a sharing-specific inbox if you prefer.
- **Legal** — `terms.html` and `privacy.html` are included as **starting templates** (clearly marked "not legal advice"). Have a lawyer review and adapt them — especially billing, liability, governing law, and your real data practices — before relying on them. They're already linked in the footer and on the start page.
- **Proof** — the landing page includes a **"See it in action"** section with stylized calendar/ledger mockups and a **testimonials** section with clearly-labelled *sample* quotes. Replace the mockups with real app screenshots and the sample quotes with real, permissioned customer testimonials before launch.
- **Analytics** — add Google Search Console verification and an analytics snippet before the closing `</body>` tag.

## Notes

- Fonts (Fraunces + Hanken Grotesk) load from Google Fonts; everything else is local.
- Illustrations are hand-built inline SVG, so nothing breaks and the page stays fast.
- Fully responsive, keyboard-accessible, and respects `prefers-reduced-motion`.
