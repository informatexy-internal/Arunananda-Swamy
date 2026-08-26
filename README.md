# Arunananda site

Single-page site for Yogi Arunananda Muni, deployed automatically to GitHub Pages via GitHub Actions.

## One-time setup

1. Create a new **public** GitHub repository (e.g. `arunananda-site`).
2. Push these files to the `main` branch (see commands below).
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **GitHub Actions** (not "Deploy from a branch").
5. Push to `main` (or re-run the workflow manually) — the site deploys automatically.
6. Your live URL will be `https://<your-username>.github.io/<repo-name>/`, shown in the workflow run summary and in Settings → Pages.

## Push these files to GitHub

From this folder:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Every future push to `main` re-runs `.github/workflows/deploy.yml` and redeploys automatically — no manual build step needed since this is a static HTML file.

## Custom domain (optional)

1. In **Settings → Pages → Custom domain**, enter your domain (e.g. `arunananda.org`).
2. Add a `CNAME` file at the repo root containing just the domain name, or let GitHub create it for you when you save the custom domain setting.
3. At your domain registrar, add either:
   - an **A record** pointing to GitHub Pages' IPs (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153), or
   - a **CNAME record** pointing `www` to `<your-username>.github.io`.
4. Wait for DNS to propagate, then enable **Enforce HTTPS** in the same settings panel.

## Updating the site

Edit `index.html` directly (it's the same file behind the Arunananda artifact), commit, and push — the workflow redeploys it automatically. Swap the placeholder WhatsApp link (`href="#"` in the "Join the WhatsApp channel" buttons) for your real invite link before going live.
