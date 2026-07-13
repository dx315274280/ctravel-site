# ctravel-site

English China Travel affiliate site for [www.ctravel.top](https://www.ctravel.top).

## Stack

- Hugo + [PaperMod](https://github.com/adityatelange/hugo-PaperMod)
- Cloudflare Pages (free CDN, no ICP)
- OpenClaw `article-crafter-travel-en` → `ctravel-to-hugo.py` publish bridge

## Local build

```bash
git submodule update --init --recursive
hugo server -D
```

## Cloudflare Pages

| Setting | Value |
|---------|-------|
| Build command | `git submodule update --init --recursive && hugo --minify` |
| Output directory | `public` |
| Environment variable | `HUGO_VERSION=0.120.0` |
| Custom domain | `www.ctravel.top` |

## DNS

See `workspace/dev-builder/scripts/ctravel-dns-setup.md` in OpenClaw repo.

## Affiliate

Replace `AFFILIATE_*` placeholders in posts after Klook/Booking approval.
Template map: `workspace/ceo/templates/ctravel-affiliate-map.json`.
