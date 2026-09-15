# acul-demo-assets

Public CDN for a `customized-consent` ACUL screen bundle, served via
[GitHub Pages](https://pages.github.com/) so the Auth0 tenant's ACUL
`head_tags` have a stable HTTPS URL to load from (instead of an ephemeral
tunnel URL).

- `assets/index.js` — the built React bundle (acul-consent-screen/dist/assets/index.js)
- `assets/index.css` — the built stylesheet

Rebuild and republish with:

```bash
cd acul-consent-screen && npm run build
cp dist/assets/index.js dist/assets/index.css /path/to/acul-demo-assets/assets/
cd /path/to/acul-demo-assets && git add -A && git commit -m "Update ACUL bundle" && git push
```

Then re-run `setup/deploy-acul.sh` (it defaults to
`https://sandijusic.github.io/acul-demo-assets` and recomputes SRI hashes
from the local build automatically) to refresh the tenant's rendering config.
