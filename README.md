# Lipoderma Website (New V3)

Static consumer site for [lipoderma.com](https://lipoderma.com), hosted from [Britecyte/lipoderma-website](https://github.com/Britecyte/lipoderma-website).

## Preview locally

```bash
cd "/Users/alexander/Desktop/Britecyte/New V3"
python3 serve.py
```

Open http://127.0.0.1:8000/

## Deployment

Hosted on **[GitHub Pages](https://pages.github.com)** from [Britecyte/lipoderma-website](https://github.com/Britecyte/lipoderma-website). Static HTML/CSS/JS from the repo root — no build step.

| Environment | Trigger | URL |
|-------------|---------|-----|
| **Production** | push to `main` | `lipoderma.com` (after DNS) |
| **GitHub Pages default** | push to `main` | https://britecyte.github.io/lipoderma-website/ |

Deploys via `.github/workflows/deploy-pages.yml` on every push to `main`.

### One-time GitHub Pages setup

1. Repo **Settings → Pages → Build and deployment**
   - Source: **GitHub Actions**
2. After the first workflow run succeeds, the site is live at the `*.github.io` URL above.
3. **Settings → Pages → Custom domain** → add `lipoderma.com` and enable **Enforce HTTPS** once DNS propagates.

### Custom domain (GoDaddy)

Remove any old Netlify DNS records first, then add:

| Type | Name | Value |
|------|------|-------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `britecyte.github.io` |

GitHub may also show repo-specific CNAME targets in **Settings → Pages** — use those if they differ.

### Retiring Netlify

1. In Netlify: **Site configuration → Delete site** (or disconnect the GitHub repo).
2. Delete the Netlify team/account when ready — hosting no longer depends on it.
