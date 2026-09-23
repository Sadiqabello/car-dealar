# Jungferngasse Flare Automobiles

Website for **Jungferngasse Flare Automobiles Nig Limited** — Next.js (App Router), TypeScript, Tailwind CSS v4, Motion and Radix Dialog.

```bash
npm install
npm run dev        # http://localhost:3000
npm run build && npm start
```

## Before launch

| What | Where |
| --- | --- |
| Phone, WhatsApp, email, address, hours, CEO name, social links | `lib/site.ts` — replace every `[PLACEHOLDER]`. Call, WhatsApp, email and directions buttons switch on automatically once a real value is set. Social links only appear when a URL is added. |
| Vehicle inventory | `lib/vehicles.ts` — the listings are **sample data**. Replace the array (or load the same `Vehicle` shape from a CMS/API). |
| Vehicle photos | `public/images/vehicles/` — referenced from `lib/vehicles.ts`. |
| Hero, interlude, About and Contact photos | `site.images` in `lib/site.ts`. |
| CEO portrait | `public/images/ceo.jpg` |
| Enquiry delivery | Set `ENQUIRY_WEBHOOK_URL` (see `.env.example`). Without it, the enquiry form returns an error in production. |
| Site URL | Set `NEXT_PUBLIC_SITE_URL` for canonical URLs, Open Graph and the sitemap. **Required** — production builds fail without it. |
| Spam protection | `/api/enquiry` has a honeypot and a per-server-instance rate limit (5 per IP per 10 min). On serverless hosts, also enable the host's firewall/rate limiting. |
| Privacy Policy / Terms | `app/privacy`, `app/terms` — have the wording reviewed before launch. |
| CEO message | `components/home/ceo-section.tsx` — confirm the wording with the CEO. |

## Placeholder photography

Vehicle, hero and interior photographs are from [Unsplash](https://unsplash.com) (Unsplash License) and are for development only. Replace them with the dealership's own photography of the actual stock.

## Structure

```
app/                      routes (home, inventory, inventory/[id], about, contact, privacy, terms, api/enquiry)
components/layout/        navbar, footer, wordmark, page header
components/home/          hero, featured collection, interlude, trust, CEO, contact CTA
components/inventory/     vehicle card/grid, filters, gallery, enquiry form + modal, vehicle actions
components/ui/            buttons, reveal animation, WhatsApp icon
lib/                      site config, vehicle data, enquiry validation, utils
```
# car-dealar
