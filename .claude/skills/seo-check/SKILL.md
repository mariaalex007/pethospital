---
name: seo-check
description: Audit a Vetri Pet Clinic page or the whole site against the project's SEO rules and report fixes. Use after building or editing a page and before launch.
---

# SEO check

Input: a page URL or slug, or `all` for every page in the sitemap in `CLAUDE.md`.

## Steps

1. Read `.claude/rules/seo.md`.
2. For each page, check:
   - Title (unique, < 60 chars, pattern from `seo.md`)
   - Meta description (140–160 chars, has a CTA)
   - Exactly one H1; heading order is logical
   - Slug matches the sitemap
   - All meaningful images have alt text; images are WebP and sized
   - ≥ 2 internal links, including Book Appointment
   - Schema present and valid: `VeterinaryCare` site-wide, plus `Service` / `FAQPage` / `BreadcrumbList` where relevant
   - NAP matches `vetri_clinic_info()` exactly
   - Canonical tag, Open Graph tags, indexable (production) or noindex (staging)
3. Where tools are available, run Lighthouse (mobile) and record Performance, Accessibility, Best Practices, SEO.

## Output

A table per page: check, status (pass / fail), fix. Fix simple issues directly; list anything that needs client input as `[TBC]`.
