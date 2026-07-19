# reroute-donate

Static "support / tip jar" page for [Re Route](https://github.com/4easterling/reroute),
the Apple Maps → Google Maps link converter. Hosted on GitHub Pages and linked from
the Re Route app's main screen.

## How it works

`index.html` is a single self-contained page (no build step, no dependencies) with a
donate button that opens a **Stripe Payment Link**. The Reroute app links to this
page's Pages URL, so the payment target can be changed here without shipping an app
update.

## Payment target (live)

The donate button points at a **live-mode** Stripe Payment Link
(`donate.stripe.com/...`, no `test_`), so it accepts real payments. It's a
pay-what-you-want tip ($1 minimum, $3 preset) on the Field Wright live account:

- Payment Link: `plink_1Tuj8K0dF6CIEMdPH5AUu4in`
- Price: `price_1Tuj7z0dF6CIEMdPDeEuNAka` (custom amount)
- Product: `prod_UuYEozMLDLfKnW` ("Re Route tip")

To change the target, create a new live Payment Link (`submit_type=donate`) and
replace the `href` on the `.donate` link in `index.html`, then commit — GitHub Pages
redeploys automatically. No change to the Reroute app is needed.
