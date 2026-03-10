# Ampz Website — ampz.app

Static website for [www.ampz.app](https://www.ampz.app).

## Deployment to NameCheap

1. Log into [NameCheap](https://www.namecheap.com/) → Dashboard → Manage (ampz.app)
2. Go to **Hosting** → **cPanel** → **File Manager**
3. Navigate to `public_html/`
4. Upload **all** contents of this `website/` directory:
   - `index.html` → `public_html/index.html`
   - `privacy.html` → `public_html/privacy.html`
   - `css/style.css` → `public_html/css/style.css`
   - `images/*` → `public_html/images/`
5. Verify at https://www.ampz.app

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
├── index.html          # Main landing page (single-page, 5 sections)
├── privacy.html        # Privacy policy (required for App Store)
├── css/
│   └── style.css       # All styles
├── images/
│   ├── app-icon.png    # App icon (used in hero)
│   ├── ampz-logo.png   # Logo with transparency
│   ├── favicon.ico     # Browser tab icon
│   ├── favicon-32.png  # 32x32 favicon
│   ├── favicon-16.png  # 16x16 favicon
│   └── apple-touch-icon.png  # iOS home screen icon
└── README.md           # This file
```

## External Dependencies

- **Google Fonts** (Inter) — loaded via CDN, gracefully falls back to system fonts
- No JavaScript dependencies
