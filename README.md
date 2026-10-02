# Duo Doodles website

A static site for GitHub Pages: the landing page, `/download` (a short link to the App
Store), `/privacy`, and `/support`.

## Before publishing

Replace the placeholders:

```sh
cd docs
# Your App Store app ID: the number in App Store Connect > App Information > Apple ID.
grep -rl 0000000000 . | xargs sed -i '' 's/0000000000/YOUR_APP_ID/g'
# Your support email.
grep -rl support@example.com . | xargs sed -i '' 's/support@example.com/you@yourdomain.com/g'
```

Add Apple's official badge: download "Download on the App Store" (black, SVG) from
https://developer.apple.com/app-store/marketing/guidelines/ and save it as
`assets/app-store-badge.svg`. Until then, the page shows an orange placeholder button.

## Publishing with GitHub Pages

1. Push this repo to GitHub.
2. Go to the repo's Settings > Pages > Build and deployment, choose "Deploy from a branch",
   pick your branch, and set the folder to `/docs`.
3. The site appears at `https://<username>.github.io/<repo>/`. For a custom domain, add it
   in the same settings page (GitHub creates the `CNAME` file).

In App Store Connect, use `…/privacy/` as the Privacy Policy URL and `…/support/` as the
Support URL. `…/` works as the Marketing URL.
