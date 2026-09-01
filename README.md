# imprecisionsystems.com

Static marketing site for **Imprecision Systems LLC**, published with GitHub Pages.

## Layout

| Path | Purpose |
|---|---|
| `index.html` | The whole site — hero, services, process, markets, brands, contact |
| `404.html` | Not-found page (GitHub Pages serves this automatically) |
| `assets/style.css` | All styling; no frameworks, no external requests |
| `assets/logo.png` | Company wordmark, used in the header and for social previews |
| `assets/mark.png` | Square version of the logo mark, used as the favicon |
| `assets/img/` | Photography — hero, statement band, and one per service card |
| `CREDITS.md` | Image provenance and licensing |
| `.nojekyll` | Disables Jekyll processing; files are served verbatim |
| `robots.txt` | Allows all crawlers, points at the sitemap |
| `sitemap.xml` | Single-URL sitemap |

There is no build step and no dependency install. Editing a file and pushing to
`main` publishes it.

## Local preview

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Publishing

1. Push to `main`.
2. In the repository, go to **Settings → Pages**, set **Source** to
   *Deploy from a branch*, branch `main`, folder `/ (root)`, and save.
3. The site becomes available at `https://imprecision-systems.github.io/www/`.

## Custom domain (`imprecisionsystems.com`)

Not enabled yet — deliberately. A `CNAME` file makes GitHub Pages redirect the
`github.io` URL to the custom domain, so committing one **before** DNS is
correct takes the site offline rather than moving it.

Order of operations:

1. At the DNS provider (currently Cloudflare) replace the existing `A` record
   for the apex with the four GitHub Pages apex addresses:

   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   and point `www` at `imprecision-systems.github.io` via `CNAME`. If Cloudflare
   proxying (the orange cloud) is on, set it to **DNS only** until GitHub has
   issued the certificate.
2. Enter the domain under **Settings → Pages → Custom domain**. GitHub writes
   the `CNAME` file itself.
3. Once the certificate is issued, tick **Enforce HTTPS**.

The relative links in `index.html` work under both the project-page path and the
apex domain; `404.html` uses root-absolute paths, which resolve correctly once
the custom domain is live.
