# Lipoderma Website (New V3)

Static consumer site for [lipoderma.com](https://lipoderma.com), hosted from [Britecyte/lipoderma-website](https://github.com/Britecyte/lipoderma-website).

## Preview locally

```bash
cd "/Users/alexander/Desktop/Britecyte/New V3"
python3 serve.py
```

Open http://127.0.0.1:8000/

## Deployment

Hosted on **[Netlify](https://www.netlify.com)**. No build step.

| Environment | Trigger | URL |
|-------------|---------|-----|
| **Production** | push to `main` | `lipoderma.com` |
| **Branch preview** | push to any other branch (e.g. `preview`) | `branch-name--lipoderma-website.netlify.app` |
| **Deploy preview** | pull request to `main` | link on the PR / Netlify dashboard |

### One-time Netlify setup

1. In the **Britecyte Netlify team**, **Add new site → Import from GitHub** → `lipoderma-website`.
2. Build settings (from `netlify.toml`):
   - Build command: *(empty)*
   - Publish directory: `.`
3. **Domain management** → add `lipoderma.com` and `www.lipoderma.com`.
4. Enable **Branch deploys** for `preview` if you want a standing staging URL.
5. Make the GitHub repo **private** if desired.

### Custom domain (GoDaddy)

Use the DNS records Netlify shows after adding the domain (replace any old GitHub Pages records).

### Access notes

- **GitHub repo:** Can be private — only org members see source on GitHub.
- **Live website:** Public. View Source / DevTools always work on any static host.
- **Data files** (e.g. `/data/providers.json`) are reachable by URL if someone knows the path.
