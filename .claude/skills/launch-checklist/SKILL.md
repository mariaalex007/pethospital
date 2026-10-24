---
name: launch-checklist
description: Run the full pre-launch testing pass for the Vetri Pet Clinic website (the "website testing" deliverable in the quotation). Use before handing the site to the client or going live.
---

# Launch checklist

Use the `qa-tester` agent to run this and report results. Fix or log every failure.

## Content

- [ ] All 13–15 pages exist and match the sitemap in `CLAUDE.md`
- [ ] No `[TBC]` placeholders, lorem ipsum or stock-photo placeholders left
- [ ] Clinic name, address, phone, WhatsApp, hours identical everywhere and match Google Business Profile
- [ ] Terms and Privacy Policy approved by the client (no `DRAFT` label)
- [ ] Spelling and grammar checked

## Functionality

- [ ] `/appointment-flow` verification passes
- [ ] WhatsApp floating button works on every page
- [ ] `tel:` links work on mobile
- [ ] Contact form sends email
- [ ] Razorpay switched to **live** keys by the client, ₹1 live UPI test done and refunded
- [ ] All social links open the correct profiles
- [ ] Google Map and reviews widget load
- [ ] No broken links (internal or external); 404 page styled

## Responsive and browsers

- [ ] 360px, 390px, 768px, 1024px, 1280px+
- [ ] Chrome (Android), Safari (iPhone), Chrome / Edge / Firefox (desktop)
- [ ] Mobile sticky Call / Book bar works and does not cover content

## Performance and accessibility

- [ ] Lighthouse mobile: Performance ≥ 85, Accessibility ≥ 95, SEO ≥ 95
- [ ] Images WebP and lazy-loaded; caching enabled
- [ ] Keyboard navigation works; focus visible; colour contrast AA

## SEO and tracking

- [ ] `/seo-check all` passes
- [ ] Production is indexable; "Discourage search engines" is off
- [ ] Sitemap submitted to Google Search Console
- [ ] Google Analytics 4 installed (if the client wants it) and noted in Privacy Policy
- [ ] Website URL added to Google Business Profile

## Security and handover

- [ ] SSL active, HTTP → HTTPS and www/non-www redirects
- [ ] Admin username is not `admin`; strong passwords; 2FA on admin accounts
- [ ] Backups scheduled on the host
- [ ] WordPress, theme and plugins up to date; premium licences registered to the client
- [ ] Client given admin access and a short how-to-edit guide

Output the checklist with pass / fail / notes, and a summary of blockers.
