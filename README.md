# Website — Uber Lin Contractor Tools (skeleton, ready to deploy)

Static site, no framework, no tracking scripts, no build step. Files in this folder are the whole site.

## Pages (9 required pages, all present)
- `index.html` — Home
- `products.html` — Products
- `product-lead-kit.html` — Product Details (hero: AI Lead Reactivation Kit v2.0, $29)
- `pricing.html` — Pricing
- `faq.html` — FAQ
- `contact.html` — Contact
- `privacy.html` — Privacy Policy
- `terms.html` — Terms of Service
- `refund.html` — Refund Policy
- `styles.css` — shared stylesheet

## Honesty notes
- No fake reviews, testimonials, sales figures, or user counts anywhere. The home page states plainly that we don't publish reviews or sales figures.
- No invented results: the Lead Kit FAQ says it guarantees a system and a refund, not income.
- Example prices in products are labelled as illustrations; the FAQ says to re-price with your own supplier prices.

## Checkout
- All Buy buttons link to Gumroad (`uberlin1.gumroad.com`), which handles payment and delivery. This site never sees card details.
- Verified Gumroad links: Estimate System `l/llpdcp`, Plywood `l/iuatrx`, Logbook `l/piqnlu`.
- Lead Kit button fixed 2026-11-20 to the exact product URL `l/ai-lead-reactivation-kit` (was store homepage). $69 bundle button fixed 2026-11-20 to the live Gumroad bundle `l/chebq` (products.html + pricing.html); it previously linked only to products.html / pricing.html with copy implying the bundle price was applied at checkout.

## Deploy (free)
1. Create a free GitHub repo, push this folder.
2. In Cloudflare Pages (free plan), connect the repo, framework preset: None, build command: none, output directory: the repo root (or this folder).
3. No domain purchase yet — use the free `*.pages.dev` URL until the user approves a domain (zero-budget rule).
4. After deploy, check every page on mobile + desktop, every Buy link, and the Privacy/Terms/Refund pages.

## Later (only after a MoR approves the product)
- Replace Gumroad checkout links with the approved checkout (Creem first, Paddle second — see `~/workspace/payment-platform-comparison-2026-11-20.md`).
- Add a signed-webhook delivery receiver on Cloudflare Workers (free tier) if selling off Gumroad: verify signature, deliver only on `transaction.completed`/`paid`, idempotency on transaction ID, revoke on approved refund/chargeback.
