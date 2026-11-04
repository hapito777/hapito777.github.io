# Inferhouse — private AI, built in-house

Static website with a VRAM / hardware sizing calculator and model advisor.
No build step, no dependencies: plain HTML, CSS and JavaScript.

## Publish on GitHub Pages

1. Create a repository, e.g. `ai-sizing` (or `<username>.github.io` to serve it at the root).
2. Upload `index.html`, `favicon.svg`, `.nojekyll` and this README to the repository root.
3. Go to **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, and save.
4. After a minute the site is live at `https://<username>.github.io/ai-sizing/`
   (or `https://<username>.github.io/` for a `<username>.github.io` repository).

Using git instead:

```bash
git init && git add . && git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<username>/ai-sizing.git
git push -u origin main
```

## Settings to change

At the top of the `<script>` block in `index.html`:

- `CONTACT_EMAIL` — your email address.
- `FORM_ENDPOINT` — optional. Create a free form at https://formspree.io and paste its endpoint
  (`https://formspree.io/f/xxxxxxx`) so requests arrive by email without the visitor's mail app.
  Leave empty to use a `mailto:` link.

Also update the brand name ("Inferhouse"), company number, address, phone, the About text, and the `GPUS` table prices.
Model data lives in the `MODELS` array; add models with their `config.json` values
(`num_hidden_layers`, `num_key_value_heads`, `head_dim`).

## Custom domain (optional)

Add a `CNAME` file containing your domain (e.g. `ai.yourcompany.com`), point a DNS CNAME record
to `<username>.github.io`, then enable **Enforce HTTPS** in Settings → Pages.
