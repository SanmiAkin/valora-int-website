# Valora International website

Static site for https://valora-int.co.uk, hosted on GitHub Pages. No build step.

Status: ready to publish except the Web3Forms access key. The site shows no email address; visitors contact the firm through the enquiry form.

## Files

| Path | What it is |
|---|---|
| `index.html` | Home page |
| `privacy.html` | Privacy notice |
| `img/` | Photos, share image (`og-image.jpg`) and logo PNG |
| `fonts/` | Cinzel and Source Sans 3, self-hosted (no Google Fonts calls) |
| `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png` | Browser and phone icons |
| `CNAME` | Custom domain for GitHub Pages: `valora-int.co.uk` |
| `robots.txt`, `sitemap.xml` | Search engine files |
| `.nojekyll` | Tells GitHub Pages to serve files as they are |

## Publish on GitHub Pages

1. Create a repository (public, or private on a paid GitHub plan) and upload every file in this folder to the root of the `main` branch.
2. Settings > Pages: Source "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Settings > Pages > Custom domain: enter `valora-int.co.uk` and save. Do this before changing DNS.
4. Optional but recommended: verify the domain in your GitHub account settings (Settings > Pages > Verified domains).
5. At the domain registrar, add these DNS records and remove any default parking records:

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | `<your-github-username>.github.io` |

6. Wait for DNS to update (up to 24 hours), then tick "Enforce HTTPS" in Settings > Pages.

## Connect the enquiry form

1. Go to https://web3forms.com, enter the inbox that should receive enquiries (any address; it is never shown on the site) and request an access key. The key arrives by email. To move enquiries to a company address later, create a new key for that address and swap it in.
2. In `index.html`, find `var ACCESS_KEY='';` and paste the key between the quotes.
3. Commit. Test by sending an enquiry from the live site.

Until the key is added, the form validates input and tells visitors it is being set up.

## Still to fill in

- After launch: add the site to Google Search Console and submit `sitemap.xml`.
