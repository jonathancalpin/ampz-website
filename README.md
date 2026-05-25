# Ampz Website — ampz.app

Static website for [www.ampz.app](https://www.ampz.app), deployed via **GitHub Pages**.

## Deployment

Pushes to `main` are deployed automatically by GitHub Pages.

- **Source:** `main` branch, repo root (`/`)
- **Custom domain:** `www.ampz.app` (CNAME file in this directory)
- **HTTPS:** enforced (cert auto-renewed)

After a push, the new build typically goes live within ~30–60 seconds. To check build status:

```bash
GITHUB_TOKEN="" gh api repos/jonathancalpin/ampz-website/pages/builds/latest \
  | jq '{status, commit, error, updated_at}'
```

## Local Preview

Open `index.html` directly in a browser, or run a local server:

```bash
cd docs/website
python3 -m http.server 8000
# Then open http://localhost:8000
```

## File Structure

```
website/
├── index.html                    # Main landing page (single-page, 6 sections)
├── privacy.html                  # Privacy policy (required for App Store)
├── Ampz-User-Manual.pdf          # Published user manual (mirror of docs/manual/output/)
├── CNAME                         # www.ampz.app (custom domain)
├── robots.txt                    # Crawl directives
├── sitemap.xml                   # Sitemap for search engines
├── css/
│   └── style.css                 # All styles
├── images/
│   ├── app-icon.png              # App icon (used in hero)
│   ├── ampz-logo.png             # Logo with transparency
│   ├── favicon.ico               # Browser tab icon
│   ├── favicon-32.png            # 32x32 favicon
│   ├── favicon-16.png            # 16x16 favicon
│   ├── apple-touch-icon.png      # iOS home screen icon
│   └── screenshots/              # In-app screenshots used in feature sections
└── README.md                     # This file
```

## Updating the User Manual

The PDF served on the site is a copy of `docs/manual/output/Ampz-User-Manual.pdf` (in the main Ampz repo). To refresh it:

```bash
# In the main Ampz repo
cd docs/manual && ./build.sh
cp output/Ampz-User-Manual.pdf "../website/Ampz-User-Manual.pdf"

# In the website repo (this directory)
git add Ampz-User-Manual.pdf
git commit -m "Refresh User Manual PDF"
git push origin main
```

## External Dependencies

- **Google Fonts** (Inter) — loaded via CDN, gracefully falls back to system fonts
- No JavaScript dependencies
