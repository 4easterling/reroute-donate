# reroute-donate

Static "support / tip jar" page for [Reroute](https://github.com/4easterling/reroute),
the Apple Maps → Google Maps link converter. Hosted on GitHub Pages and linked from
the app's main screen.

## How it works

`index.html` is a single self-contained page (no build step, no dependencies) with a
donate button that opens a **Stripe Payment Link**. The Reroute app links to this
page's Pages URL, so the payment target can be changed here without shipping an app
update.

## Going live (test → live)

The donate button currently points at a **test-mode** Stripe Payment Link
(`donate.stripe.com/test_...`), which only accepts [Stripe test cards](https://docs.stripe.com/testing).

To accept real payments:

1. In the Stripe Dashboard (live mode), recreate the product + pay-what-you-want price
   and a Payment Link (`submit_type=donate`).
2. Replace the `href` on the `.donate` link in `index.html` with the live URL
   (`donate.stripe.com/...`, no `test_`).
3. Commit — GitHub Pages redeploys automatically.

No change to the Reroute app is needed.
