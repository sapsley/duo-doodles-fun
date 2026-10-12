# Duo Doodles website

A static site for GitHub Pages: the landing page, `/download` (a short link to the App
Store), `/privacy`, and `/support`.

## Before publishing

The App Store links already use the app's ID (6818603832), and the support email is
support@duodoodles.fun.

Add Apple's official badge: download "Download on the App Store" (black, SVG) from
https://developer.apple.com/app-store/marketing/guidelines/ and save it as
`assets/app-store-badge.svg`. Until then, the page shows an orange placeholder button.

## Publishing with GitHub Pages

The site lives in the app repo's `docs/` folder and is published to its own repo,
https://github.com/sapsley/duo-doodles-fun, with `docs/` as that repo's root. After
committing site changes in the app repo, publish them from the app repo's root with:

```sh
git subtree push --prefix=docs site main
```

(`site` is the git remote for the site repo.)

One-time setup:

1. In the site repo, go to Settings > Pages > Build and deployment, choose "Deploy from a
   branch", and pick `main` with the `/ (root)` folder.
2. Under Custom domain, enter `duodoodles.fun` (already in `CNAME`), and turn on
   Enforce HTTPS once GitHub has issued the certificate.
3. At your domain registrar, add these DNS records for `duodoodles.fun`:
   - `A` records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `AAAA` records: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`
   - `CNAME` for `www` pointing to `<username>.github.io`
   Leave the registrar's `MX` records alone, so the mailbox keeps working.

In App Store Connect, use `https://duodoodles.fun/privacy/` as the Privacy Policy URL and
`https://duodoodles.fun/support/` as the Support URL. `https://duodoodles.fun/` works as the
Marketing URL.
