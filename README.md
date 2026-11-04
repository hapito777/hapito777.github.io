# Inferhouse — private AI, built in-house

Company website with a plain-language cost estimate, a detailed GPU/VRAM calculator,
a ranked catalogue of current open AI models, and SEO metadata.
Plain HTML, CSS and JavaScript — no build step.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The website |
| `favicon.svg`, `apple-touch-icon.png` | Browser and phone icons |
| `og-image.png` | Preview image when the link is shared (LinkedIn, WhatsApp, Slack…) |
| `robots.txt`, `sitemap.xml` | Tell search engines what to index |
| `.nojekyll` | Stops GitHub from processing the files |

## 1. Set your site address (important for SEO)

The files use the placeholder `https://YOUR-USERNAME.github.io/inferhouse/`.
Replace it everywhere with your real address — it appears in `index.html`, `robots.txt` and `sitemap.xml`:

```bash
grep -rl "YOUR-USERNAME.github.io/inferhouse/" . | xargs sed -i 's#https://YOUR-USERNAME.github.io/inferhouse/#https://yourname.github.io/inferhouse/#g'
```

Use the exact URL the site is served from, ending with `/`. If you later use your own domain, run the replace again with it.

## 2. Publish on GitHub Pages

1. Create a repository named `inferhouse` (or `<username>.github.io` to serve from the root — then your address has no `/inferhouse/`).
2. Upload all files above to the repository root.
3. **Settings → Pages** → Deploy from a branch → `main` / `(root)` → Save.

## 3. Get found on Google

1. Open [Google Search Console](https://search.google.com/search-console), add your site address, and verify it
   (choose the *HTML tag* method and paste the `<meta name="google-site-verification" …>` tag into the `<head>` of `index.html`).
2. In Search Console → **Sitemaps**, submit `sitemap.xml`.
3. Do the same in [Bing Webmaster Tools](https://www.bing.com/webmasters) (you can import from Google in one click).
4. Check the structured data with Google’s [Rich Results Test](https://search.google.com/test/rich-results).
5. Create a free **Google Business Profile** and a **LinkedIn company page** that link to the site.

## Settings in `index.html`

At the top of the `<script>` block:

- `CONTACT_EMAIL` — where enquiries go (currently sord23@gmail.com).
- `FORM_ENDPOINT` — optional [Formspree](https://formspree.io) endpoint so the form sends messages directly.

Also fill in the footer placeholders: company number, registered address and phone.
Update GPU prices in the `GPUS` array and models in the `MODELS` array as the market changes.
