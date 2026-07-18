# onurbulut-portfolio

Personal portfolio site for **Onur Bulut** — Senior Mobile Software Engineer (Flutter & Native iOS).

A single, self-contained `index.html`: no build step required to deploy, no external
requests (all CSS, JS and images are inlined). Bilingual **TR / EN** with a language
switch, light/dark theme, and real product screenshots embedded as data URIs.

## Deploy

`index.html` is fully static — serve it anywhere:

- **GitHub Pages** — push to GitHub, enable Pages on the default branch (root). Done.
- **Netlify / Vercel / Cloudflare Pages** — point at the repo, no build command, output dir `/`.
- **Any static host / your own domain** — just upload `index.html`.

Local preview:

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## Editing the content

The root `index.html` is generated — don't hand-edit it. Instead:

1. Edit `build/portfolio.template.html` (copy lives there; image slots are
   `{{GAIA}}`, `{{NYBBLE}}`, `{{TURAPP}}`, `{{ICON_DERSIM}}`, `{{ICON_MIZANCO}}`,
   `{{ICON_MENUPAL}}`).
2. Rebuild:

   ```bash
   python3 build/build.py
   ```

3. Commit the regenerated `index.html`.

### Translations

Every translatable element carries a `data-tr="…"` attribute holding the Turkish
string; the English is the element's default markup. The page auto-captures the
English on load, so to change copy you edit the visible (EN) text and/or the
`data-tr` attribute in the template.

### Images

Image data URIs are stored in `build/assets.json`. To regenerate them from source
screenshots (live Gaia capture, Nybble golden-test PNGs, App Store icons, the
TUR Assist screen), see `build/mkimg.py` — it needs the original project files
on disk and Pillow (`pip install pillow`).

## What's inside

- **Hero** — positioning, headline stats, and per-stack experience bars.
- **Live on the App Store** — Dersim, Mizanço, MenuPal (App Store + Google Play links).
- **Selected work** — LifeOS, Ürün Panel, Tamirci, Gaia Botanique (live screenshot), Nybble.
- **Experience** — full role timeline + education.
- **Earlier apps** — TUR Assist, Otokonfor (RS Automotive Group).
- **How I work** and **Contact**.

## Structure

```
index.html                     # built, deployable, self-contained
build/
  portfolio.template.html      # editable source (image slots = {{...}})
  assets.json                  # inlined image data URIs
  build.py                     # template + assets.json -> ../index.html
  mkimg.py                     # (reference) regenerate assets.json from source images
```

---

Contact: 10urbulut@gmail.com · [linkedin.com/in/10urbulut](https://linkedin.com/in/10urbulut) · [github.com/10urbulut](https://github.com/10urbulut)
