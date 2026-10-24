# Design system

Applies to all design and front-end work.

## Brand feel

Warm, caring, clean and clinical-but-friendly. Pet owners are often worried; the site should feel calm and reassuring, and make the next step (book / call / WhatsApp) obvious.

## Colours (proposed — confirm with client; replace if they have a logo palette)

| Token | Hex | Use |
|---|---|---|
| `--vetri-primary` | `#0F766E` | Teal: header, primary buttons, links |
| `--vetri-primary-dark` | `#115E59` | Hover states, footer |
| `--vetri-accent` | `#F59E0B` | Warm amber: highlights, badges, secondary CTA |
| `--vetri-whatsapp` | `#25D366` | WhatsApp buttons only |
| `--vetri-ink` | `#1F2937` | Body text |
| `--vetri-muted` | `#6B7280` | Secondary text |
| `--vetri-surface` | `#F7FAF9` | Section backgrounds |
| `--vetri-white` | `#FFFFFF` | Cards, page background |

- Define colours once in `theme.json` / the Kadence global palette. Never hardcode hex values in patterns or pages.
- All text/background pairs must meet WCAG AA contrast (4.5:1 body, 3:1 large text).

## Typography

- Headings: **Poppins** (600/700). Body: **Inter** (400/500). Self-host the fonts (no Google Fonts CDN) for speed and privacy.
- Base size 16px mobile, 17–18px desktop. Line height 1.6 for body.
- One H1 per page.

## Layout

- Mobile first. Breakpoints: 360, 768, 1024, 1280px. Max content width 1200px.
- Spacing scale: 4, 8, 12, 16, 24, 32, 48, 64, 96px.
- Cards: 12px radius, subtle shadow. Buttons: 8px radius, min height 48px (touch target).

## Always-visible actions

- **WhatsApp floating button**: bottom-right on every page, green, with tooltip "Chat with us".
- **Mobile sticky bar** (< 768px): two buttons, "Call" and "Book Appointment".
- Header: logo, menu, phone number and a "Book Appointment" button.

## Imagery

- Prefer real photos of the clinic, team and patients (with owner permission). Stock photos only as placeholders, marked `[TBC: replace with clinic photo]`.
- No graphic surgical or injury images.
- WebP, lazy-loaded below the fold, explicit width/height, meaningful alt text.
- Icons: one consistent outline icon set (e.g. Lucide/Phosphor SVGs).
