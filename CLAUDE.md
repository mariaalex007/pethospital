# Vetri Pet Clinic website

Client website for **Vetri Pet Clinic**, a veterinary clinic in Tamil Nadu, India. The full scope, pricing and payment terms are in `docs/project-brief.md`. Read it before starting any new feature.

## Goal

A fast, trustworthy, mobile-first site whose main job is to **get pet owners to book an appointment** (form → clinic WhatsApp) or call. Every page should lead to that action.

## Stack

- **WordPress** (latest stable), PHP 8.2+
- **Theme:** premium parent theme + our child theme `vetri-child` in `wp-content/themes/vetri-child/`
  - Default choice: **Kadence** (free theme) + **Kadence Pro / Kadence Blocks Pro**. Confirm with the client before purchase; Astra Pro is the fallback.
- **Editor:** Gutenberg block editor with our own **block patterns**. No Elementor or other heavy page builders.
- **Forms:** Fluent Forms (appointment form, contact form)
- **Payments:** Razorpay (UPI, cards, net banking)
- **SEO:** Rank Math
- **Performance:** LiteSpeed Cache or WP Rocket (depends on host), images as WebP
- **Local dev:** `@wordpress/env` (Docker)

## Fast development method

We build the site from a small set of reusable parts instead of designing each page by hand.

1. **Local first:** `npx @wordpress/env start` → http://localhost:8888 (admin / password).
2. **Patterns once, pages many:** build these block patterns in `vetri-child/patterns/` first: hero, service card grid, CTA band (WhatsApp + Call), FAQ, testimonials, gallery grid, map + clinic hours, trust badges. Every page is assembled from them.
3. **One service template:** all 6 service pages share one layout. Use the `/new-service-page` skill.
4. **Content first, in Markdown:** page copy lives in `docs/content/<slug>.md` before it goes into WordPress, so it can be reviewed with the client.
5. **One source of truth for clinic info:** phone, WhatsApp number, address, hours and social links are defined once in `vetri-child/inc/clinic-info.php` and output via shortcodes or functions. Never hardcode them in pages.
6. **Work in parallel with agents:** content writer drafts copy while the developer builds patterns; the SEO and QA agents review before each milestone.

## Sitemap (15 pages)

| # | Page | Slug |
|---|---|---|
| 1 | Home | `/` |
| 2 | About Us | `/about-us/` |
| 3 | Services (hub) | `/services/` |
| 4–9 | 6 service pages | `/services/<service>/` |
| 10 | Reviews | `/reviews/` |
| 11 | Gallery | `/gallery/` |
| 12 | Book Appointment | `/book-appointment/` |
| 13 | Contact Us | `/contact-us/` |
| 14 | Terms & Conditions | `/terms-and-conditions/` |
| 15 | Privacy Policy | `/privacy-policy/` |

The 6 services are **not yet confirmed**. Working list until the client confirms: General Consultation & Vaccination, Surgery, Diagnostics & Lab, Dental Care, Grooming, Emergency & Critical Care.

## Required features (from the quotation)

- Premium colours, mobile-responsive design → `.claude/rules/design-system.md`
- Social media integration → `.claude/rules/integrations.md`
- WhatsApp sidebar button on every page and appointment form whose details reach the clinic's WhatsApp → `.claude/rules/integrations.md`, `/appointment-flow`
- Payment gateway with UPI → `.claude/rules/integrations.md`
- Google Business Profile (GMB) integration → `.claude/rules/integrations.md`
- Basic SEO → `.claude/rules/seo.md`, `/seo-check`
- Website testing → `/launch-checklist`

## Working rules

- **Never invent clinic facts.** Doctor names, qualifications, prices, timings, addresses and reviews come only from the client. Use `[TBC: what is needed]` placeholders until then.
- **Never write fake reviews or testimonials.** Show real Google reviews only.
- Edit only the child theme, `mu-plugins` and docs. Never edit WordPress core, the parent theme or third-party plugins.
- Do not commit WordPress core, `uploads/`, premium theme/plugin ZIPs, licence keys, API keys or `.env` files.
- Mobile first: design and test at 360px width before desktop.
- Every page ends with a booking CTA (WhatsApp + Call).
- Keep pages fast: target Lighthouse mobile Performance ≥ 85, Accessibility ≥ 95, SEO ≥ 95.

## Agents (`.claude/agents/`)

| Agent | Use for |
|---|---|
| `wp-developer` | Child theme, block patterns, PHP, plugin configuration, integrations |
| `ui-designer` | Layout, colours, typography, responsive behaviour, design review |
| `content-writer` | Page copy, service descriptions, FAQs, policies drafts |
| `seo-specialist` | Titles, meta, schema, local SEO, Google Business Profile |
| `qa-tester` | Testing before each milestone and before launch (read-only) |

## Skills (`.claude/skills/`)

| Skill | What it does |
|---|---|
| `/new-service-page` | Creates a service page from the shared template, with content, SEO and schema |
| `/appointment-flow` | Builds or checks the appointment form → WhatsApp → email flow |
| `/seo-check` | Audits one page or the whole site against `seo.md` |
| `/launch-checklist` | Full pre-launch testing pass (the "website testing" deliverable) |

## Open items from the client

- [ ] Final list of 6 services
- [ ] Clinic name as on Google, full address, phone, WhatsApp number, opening hours
- [ ] Logo, brand colours (if any), real clinic and team photos
- [ ] Doctor names and qualifications
- [ ] Social media profile links
- [ ] Google Business Profile manager access
- [ ] Razorpay account (KYC) for UPI payments, and what payments are for (consultation advance, full fees?)
- [ ] Domain name choice
- [ ] Languages: English only, or English + Tamil?
