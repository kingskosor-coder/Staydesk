# StayDesk on Netlify
Deploy: push this folder to Git and import in Netlify (or `netlify deploy --prod`). Functions need a build step, so drag-and-drop of the plain folder is not enough.

Environment variables (Site settings → Environment):
- STAFF_KEY  – shared password staff enter on first load (recommended)
- ICAL_TOKEN – optional; append ?t=TOKEN to export feed URLs
- SENDGRID_KEY, MAIL_FROM – enable "Send email now"
- TWILIO_SID, TWILIO_TOKEN, TWILIO_FROM – enable "Send SMS now"
Data is stored in Netlify Blobs (shared by all staff).
- PAYSTACK_SECRET – your Paystack secret key (sk_live_… / sk_test_…) for USD payment links

Paystack setup:
1. Ask Paystack support to enable USD on your account (needs completed verification).
2. Dashboard → Settings → API & Webhooks → set Webhook URL to https://YOUR-SITE/api/paystack-webhook
3. In a booking, tap "Add USD payment link", then send the message. Paid amounts update automatically.
