# Integrations

All contact details come from `vetri_clinic_info()` in `inc/clinic-info.php`. Never hardcode them.

## WhatsApp sidebar button

- Floating button on every page linking to `https://wa.me/<number>?text=<encoded greeting>`.
- Number format for links: country code without `+` or spaces, e.g. `91XXXXXXXXXX`.
- Default text: "Hi Vetri Pet Clinic, I would like to book an appointment."
- Add via `mu-plugins/vetri-core.php` (lightweight) rather than a plugin.

## Appointment form → clinic WhatsApp (fast method, no paid API)

1. Fluent Forms form on `/book-appointment/` and in a pattern used on service pages.
2. Fields: owner name, phone (10-digit Indian mobile, validated), pet name, pet type (Dog / Cat / Bird / Other), breed (optional), pet age, service (dropdown of the 6 services), preferred date, preferred time slot, symptoms / notes, consent checkbox.
3. On submit:
   - Save the entry in WordPress and **email** it to the clinic.
   - Redirect the user to `wa.me/<clinic number>` with a pre-filled message containing all appointment details, so the request lands in the clinic's WhatsApp.
4. Show a thank-you message explaining that the clinic will confirm the slot on WhatsApp.

Upgrade path (out of scope, change request): automatic messages via the WhatsApp Business API.

Use the `/appointment-flow` skill to build or verify this.

## Payment gateway (UPI)

- **Razorpay**: supports UPI (GPay, PhonePe, Paytm, BHIM), cards and net banking.
- Use Razorpay Payment Button / Payment Page or the Fluent Forms Razorpay integration. No WooCommerce unless products are added later.
- Test fully in Razorpay **test mode** with test keys before going live. Live keys are entered by the client on the server.
- Confirm with the client what payments are for before building (consultation advance, full fees, etc.).

## Google Business Profile (GMB)

- Contact page: embedded Google Map (click-to-load facade) + "Get directions" link.
- Reviews page and Home: show real Google reviews via a reviews widget plugin or the Places API; link "Write a review" to the GBP review URL.
- Name, address and phone on the site must match the GBP listing exactly.
- Link the website URL from the GBP listing after launch.

## Social media

- Icons in header/footer linking to the clinic's profiles (Instagram, Facebook, YouTube as applicable).
- Open Graph and Twitter Card tags on every page (handled by Rank Math).
- Optional Instagram feed on Gallery or Home, lazy-loaded.

## Call

- Use `tel:+91XXXXXXXXXX` links. Phone number visible in header and footer, and in the mobile sticky bar.
