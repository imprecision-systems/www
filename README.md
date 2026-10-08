# imprecisionsystems.com

Static marketing site for **Imprecision Systems LLC**, published with GitHub Pages.

## Layout

| Path | Purpose |
|---|---|
| `index.html` | Home page — hero, services, why it lasts, brands, process, markets, contact |
| `technology.html` | Technology page — AI-driven bring-up, firmware supply-chain security, AI engine, statement band |
| `404.html` | Not-found page (GitHub Pages serves this automatically) |
| `assets/style.css` | All styling; no frameworks, no external requests |
| `assets/logo.png` | Company wordmark, used in the header and as the JSON-LD Organization logo |
| `assets/mark.png` | Square version of the logo mark, used as the favicon |
| `assets/img/` | Photography — hero and statement band backgrounds |
| `CREDITS.md` | Image provenance and licensing |
| `CNAME` | Custom domain for GitHub Pages (`imprecisionsystems.com`) |
| `.nojekyll` | Disables Jekyll processing; files are served verbatim |
| `robots.txt` | Allows all crawlers, points at the sitemap |
| `sitemap.xml` | Sitemap of both pages |

There is no build step and no dependency install. GitHub Pages serves `main`
from the repository root.

This repository is a published snapshot: each release replaces its single
commit, and it does not accept pull requests.

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```
