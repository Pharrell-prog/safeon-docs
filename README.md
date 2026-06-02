## Safeon Docs (MkDocs)

Engineering documentation site (MkDocs + Material).

### Run locally

```powershell
cd "C:\Users\Pharrell\Documents\M7\safeon-docs"
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
mkdocs serve
```

Open `http://127.0.0.1:8000/`.

### Deploy (GitHub Pages — use this, not Cloudflare)

Cloudflare’s “Create application” flow forces a Wrangler deploy command and often fails with token errors. **Use GitHub Pages instead.**

1. Push this repo to GitHub (`Pharrell-prog/safeon-docs`).
2. On GitHub: **Settings → Pages → Build and deployment → Source** → choose **GitHub Actions**.
3. Push to `main` (the workflow in `.github/workflows/pages.yml` builds and deploys automatically).
4. Live URL: `https://pharrell-prog.github.io/safeon-docs/` (after the first Actions run finishes).

### Custom domain (Porkbun)

1. GitHub repo → **Settings → Pages → Custom domain** → enter e.g. `docs.yourdomain.com`.
2. Porkbun DNS:
   - **Type**: CNAME  
   - **Host**: `docs`  
   - **Answer**: `pharrell-prog.github.io`
3. Update `site_url` in `mkdocs.yml` to match your real domain.

### Content

- Markdown: `docs/`
- Images: `docs/assets/`
- PDS: `docs/pds/safeon-oxman-sft-001.md`
