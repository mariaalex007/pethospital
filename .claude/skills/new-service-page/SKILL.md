---
name: new-service-page
description: Create one of the 6 Vetri Pet Clinic service pages from the shared service template, with copy, SEO, schema and booking CTAs. Use when adding or rebuilding a service page.
---

# New service page

Input: the service name (e.g. "Dental Care"). If not given, ask which of the services listed in `CLAUDE.md` to build.

## Steps

1. Read `CLAUDE.md`, `.claude/rules/content.md`, `.claude/rules/seo.md` and `.claude/rules/design-system.md`.
2. Choose the slug: `/services/<kebab-case-name>/`.
3. Draft copy in `docs/content/services/<slug>.md` (use the `content-writer` agent for longer copy) with this structure:
   - Front matter: `title`, `meta_description`, `h1`, `primary_keyword`
   - Hero: H1 + one-line benefit + Book / WhatsApp buttons
   - What this service includes (4–6 points)
   - When to bring your pet (signs to watch for)
   - What to expect during the visit (3–4 steps)
   - Why Vetri Pet Clinic (only client-confirmed facts; otherwise `[TBC]`)
   - FAQs (4–6 questions)
   - Booking CTA band
4. Build the page in WordPress from patterns in this order: `vetri/hero-service`, `vetri/feature-list`, `vetri/steps`, `vetri/faq`, `vetri/cta-band`. Create a missing pattern in `vetri-child/patterns/` instead of styling the page by hand.
5. SEO: set title and meta in Rank Math, add `Service` + `FAQPage` + breadcrumb schema, link to 2 related services and to `/book-appointment/`.
6. Add the service to: the Services hub grid, the main menu "Services" dropdown, and the appointment form's service dropdown.
7. Run `/seo-check` on the new page and fix what it reports.

## Done when

- Copy has no invented facts; every unknown is a `[TBC]` placeholder.
- Page looks right at 360px and 1280px.
- `/seo-check` passes.
