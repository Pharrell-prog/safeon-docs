## Safeon Docs (MkDocs)

This folder is a ready-to-deploy documentation site built with **MkDocs + Material**.

### What you do
- **You will login** to GitHub + Cloudflare Pages + Porkbun (domain/DNS).
- You will connect this repo to Cloudflare Pages and point `docs.<yourdomain>` to it.

### 1) Run locally (optional)

From PowerShell in this folder:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
mkdocs serve
```

Then open the local URL shown (usually `http://127.0.0.1:8000/`).

### 2) Deploy (Cloudflare Pages – recommended)

1. Create a new GitHub repo (example name: `safeon-docs`) and push this folder.
2. In Cloudflare Pages:
   - **Connect to Git** → select the repo
   - **Framework preset**: None
   - **Build command**: `mkdocs build`
   - **Build output directory**: `site`
3. After deploy, Cloudflare will give you a URL like:
   - `<project>.pages.dev`

### 3) Custom domain (Porkbun DNS)

In Porkbun DNS, add:
- **Type**: CNAME  
  **Host**: `docs`  
  **Answer**: `<project>.pages.dev`

Then in Cloudflare Pages → Custom domains:
- Add: `docs.<yourdomain>`

### Notes
- Edit content in `docs/` (Markdown).
- Images live in `docs/assets/`.
- Your PDS page is at `docs/pds/safeon-oxman-sft-001.md`.

