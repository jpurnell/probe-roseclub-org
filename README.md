# probe.roseclub.org

Static source for the `apple-app-site-association` file that lets the PasskeyProbe example app in
SwiftWebAuthnClient use `probe.roseclub.org` as a WebAuthn relying party.

Hosted on **Netlify** (drag-and-drop deploy of this folder), with the `probe` CNAME in Squarespace DNS
pointing at the Netlify site. It was first tried on GitHub Pages, but GitHub never issued a certificate
for the custom domain, so Pages is turned off.

- `aasa/apple-app-site-association` is the file. It lives in a plain folder because Netlify's drop skips
  dot-folders; `_redirects` rewrites (status 200, not a redirect) `/.well-known/apple-app-site-association`
  to it, since Apple requires no redirects.
- `_headers` serves it as `application/json`.

To redeploy, drag this folder (without `.git`) onto the site's Deploys page.
