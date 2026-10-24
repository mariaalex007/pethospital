# Basic SEO

## Every page

- Unique `<title>` under 60 characters: `<Page topic> | Vetri Pet Clinic, <Area>`.
- Meta description 140–160 characters with a call to action.
- One H1 containing the main keyword; logical H2/H3 structure.
- Clean slug (see sitemap in `CLAUDE.md`).
- Alt text on all meaningful images; decorative images get empty alt.
- At least 2 internal links (to a service page and to Book Appointment).
- Open Graph image set.

## Local SEO

- Target "vet / veterinary clinic / pet hospital in <area>" and "<service> for dogs/cats in <area>" keywords.
- NAP (name, address, phone) identical everywhere: footer, Contact page, schema and Google Business Profile.
- Add `VeterinaryCare` structured data (subtype of `LocalBusiness`) site-wide with name, address, geo, phone, opening hours, `sameAs` social links and URL.
- Service pages: `Service` schema with `provider` pointing to the clinic, and `FAQPage` schema when the page has FAQs.
- Breadcrumb schema on all inner pages.

## Technical

- XML sitemap via Rank Math, submitted to Google Search Console.
- `robots.txt` allows crawling on production; staging must be set to noindex.
- HTTPS everywhere, one canonical domain (www or non-www) with redirects.
- Core Web Vitals: LCP < 2.5s, CLS < 0.1, INP < 200ms on mobile.
- No duplicate content between service pages; each needs its own copy.

Use `/seo-check` to audit a page.
