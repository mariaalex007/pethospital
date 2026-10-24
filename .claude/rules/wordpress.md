---
paths:
  - "wp-content/**"
  - ".wp-env.json"
---

# WordPress code rules

## Where code goes

- All theme code in `wp-content/themes/vetri-child/`. Never edit the parent theme, core or third-party plugins.
- Site-wide functionality that must survive a theme change (clinic info, schema, WhatsApp button) goes in `wp-content/mu-plugins/vetri-core.php`.
- Child theme layout:
  - `style.css` (theme header only), `functions.php` (loads `inc/` files), `theme.json` (palette, fonts, spacing)
  - `inc/clinic-info.php` — single source of truth for NAP, hours, WhatsApp number, social links
  - `patterns/` — block patterns, one file each, registered with category `vetri`
  - `assets/css/`, `assets/js/`, `assets/fonts/`

## PHP

- Prefix everything with `vetri_` (functions, options, hooks, shortcodes) and text domain `vetri`.
- Escape all output (`esc_html`, `esc_attr`, `esc_url`, `wp_kses_post`). Sanitise all input. Use nonces on forms.
- Enqueue CSS/JS with `wp_enqueue_style` / `wp_enqueue_script`; never inline `<script>` tags in templates. Load JS with `defer`.
- No direct database queries unless unavoidable; use `$wpdb->prepare` if so.
- Follow WordPress Coding Standards.

## Blocks and patterns

- Build pages with core blocks + Kadence Blocks. Assemble pages from our patterns.
- Patterns use palette and spacing presets from `theme.json`, never hardcoded values.
- Keep plugin count low. Before adding a plugin, check whether a pattern or a few lines in `mu-plugins` would do.

## Performance

- No jQuery-dependent code of our own. Vanilla JS only.
- Images: WebP, `loading="lazy"` below the fold, hero image preloaded.
- Google Maps: load as a click-to-load facade, not on page load.

## Secrets

- API keys (Razorpay, Google) live in `wp-config.php` constants or plugin settings on the server, never in git.
