---
name: appointment-flow
description: Build or verify the Vetri Pet Clinic appointment flow — form, email notification and pre-filled WhatsApp message to the clinic, plus optional UPI payment. Use when setting up, changing or testing appointment booking.
---

# Appointment flow

Read `.claude/rules/integrations.md` first. It defines the fields and the flow.

## Build

1. Confirm the clinic WhatsApp number exists in `vetri_clinic_info()`. If it is a placeholder, stop and say so.
2. Create the form in Fluent Forms with the fields from `integrations.md`. Validate phone as a 10-digit Indian mobile number. Preferred date must not be in the past.
3. Service dropdown must match the current service pages exactly.
4. Notifications: email the entry to the clinic's address; save entries in WordPress.
5. Confirmation: redirect to `https://wa.me/<number>?text=<message>` where the message is URL-encoded and formatted like:

   ```
   New appointment request – Vetri Pet Clinic
   Owner: {name}
   Phone: {phone}
   Pet: {pet_name} ({pet_type}, {breed}, {age})
   Service: {service}
   Preferred: {date}, {time_slot}
   Notes: {notes}
   ```

6. Thank-you message: "Thank you! We have received your request and will confirm your slot on WhatsApp."
7. If payments are confirmed by the client: add the Razorpay step (test mode) after form submission and before the WhatsApp redirect.
8. Embed the form as a pattern (`vetri/appointment-form`) on `/book-appointment/` and reuse it on service pages.

## Verify (run every time the flow changes)

- [ ] Required-field and phone validation work
- [ ] Email arrives at the clinic address
- [ ] WhatsApp opens with all details correctly filled on Android, iPhone and desktop (WhatsApp Web)
- [ ] Special characters and Tamil text in notes survive encoding
- [ ] Razorpay test payment with UPI succeeds and failure is handled (if enabled)
- [ ] Consent checkbox is required and links to the Privacy Policy
- [ ] Spam protection (honeypot or Turnstile) is on

Report results as a checklist with pass/fail and fixes made.
