# L'MSMEEN — Moroccan Msemen Street Food

A responsive bilingual (French / Arabic) front-end prototype for a Moroccan msemen food truck.

## Included

- Landing page and L'MSMEEN visual identity.
- Product menu with category filters and search.
- Msemen customizer with live price estimate.
- Shopping cart with quantity controls.
- Demo checkout and local order receipt.
- Weekly demo schedule and a local demo admin editor.
- QR code generated from the current website URL and a download button.
- French / Arabic language switch with RTL layout.
- Responsive mobile layout.
- GitHub Pages deployment workflow.

## Run locally

No build tools are required.

1. Download and extract the ZIP.
2. Open `index.html` in a browser.
3. For a more realistic local preview, run a simple static server from this folder, for example:

   ```bash
   python -m http.server 8000
   ```

4. Open `http://localhost:8000`.

The QR code in a local preview points to the local URL. It becomes a shareable QR code after the site is published to a public URL.

## Publish on GitHub Pages

1. Sign in to GitHub and create a **public** repository named `lmsmeen` (or any name you prefer).
2. Upload the contents of this folder to the repository root. Make sure `index.html` is at the root, not inside another nested folder.
3. Commit the files to the `main` branch.
4. Open **Settings → Pages** in the repository.
5. Under **Build and deployment**, choose **GitHub Actions** as the source.
6. Open the **Actions** tab and wait for the workflow named **Deploy L'MSMEEN to GitHub Pages** to finish.
7. GitHub will show the published URL under **Settings → Pages**. Open it, then scan/download the QR code from the QR section of the website.

The included workflow is `.github/workflows/pages.yml`.

Official guide: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Important before any real launch

This is a student project prototype, not a live restaurant ordering system.

- Product names, descriptions, menu prices, locations and hours are illustrative demo content. Confirm every item with the team before presenting it as real.
- Orders, recipe suggestions and schedule edits are stored in the visitor's browser using `localStorage`. They are **not** sent to a central database and are not visible to other visitors or devices.
- The demo admin button is intentionally not protected. Do not use it to manage a real business.
- No online payment is connected. No real delivery or pickup service is running.
- Before enabling WhatsApp order handoff, edit `CONFIG.whatsappNumber` near the top of `app.js` and set the full Moroccan international number using digits only, e.g. `2126XXXXXXXX`.
- A real deployment needs a backend or trusted ordering provider for shared orders, inventory, schedule updates, admin authentication and customer data protection.
- Confirm food safety, vehicle conversion, food activity and public-space permissions with the relevant Moroccan authorities and the institution before operating a real food truck.

## Replace the demo truck artwork with your Blender render

The current hero uses `assets/truck.svg` as a lightweight illustrated placeholder. You can replace that artwork with your own render:

1. Export a transparent PNG from Blender, for example `assets/truck-render.png`.
2. In `index.html`, find `src="assets/truck.svg"` and change it to `src="assets/truck-render.png"`.
3. Keep the image wide (roughly 16:9 or 3:2), with transparent background if possible.

If you later export a `.glb` model, you can add Google's `<model-viewer>` component for a rotatable 3D truck. The current prototype intentionally stays lightweight and does not require a 3D library.

## Project structure

```text
lmsmeen-site/
├── index.html
├── styles.css
├── app.js
├── site.webmanifest
├── .nojekyll
├── README.md
├── assets/
│   ├── truck.svg
│   ├── msemen-creator.svg
│   ├── msemen-fold.svg
│   ├── msemen-*.svg
│   └── favicon.svg
└── .github/workflows/pages.yml
```