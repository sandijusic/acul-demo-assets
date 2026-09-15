# sofi-acul-assets

Public CDN for the SoFi `customized-consent` ACUL screen bundle, served via
[GitHub Pages](https://pages.github.com/) so the Auth0 tenant's ACUL
`head_tags` have a stable HTTPS URL to load from (instead of an ephemeral
tunnel URL).

- `assets/index.js` — the built React bundle (acul-consent-screen/dist/assets/index.js)
- `assets/index.css` — the built stylesheet

Rebuild and republish with:

```bash
cd acul-consent-screen && npm run build
cp dist/assets/index.js dist/assets/index.css /path/to/sofi-acul-assets/assets/
cd /path/to/sofi-acul-assets && git add -A && git commit -m "Update ACUL bundle" && git push
```

Then re-run `setup/deploy-acul.sh https://sandijusic.github.io/sofi-acul-assets`
to refresh the SRI hashes on the tenant's rendering config.
