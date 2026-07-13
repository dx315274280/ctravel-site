# ctravel-site

English China Travel affiliate site for [www.ctravel.top](https://www.ctravel.top).

## Stack

- Hugo + [PaperMod](https://github.com/adityatelange/hugo-PaperMod)
- Cloudflare **Workers** 静态托管（Pages 已并入 Workers，控制台不再单独显示 Pages）
- OpenClaw `article-crafter-travel-en` → `ctravel-to-hugo.py` publish bridge

## Local build

```bash
git submodule update --init --recursive
hugo server -D
```

## Cloudflare Workers（Hugo 静态站）

| 设置项 | 在哪里填 | 值 |
|--------|----------|-----|
| Build command | Settings → Build → Build configuration ✏️ | `git submodule update --init --recursive && hugo --minify` |
| **Build output** | 仓库 `wrangler.jsonc` 的 `assets.directory` | **`./public`**（已在 Git 里，不用在 UI 找） |
| Deploy command | Build configuration | `npx wrangler deploy` |
| **Environment variable** | Settings → Build → **Variables and secrets** → **+** | `HUGO_VERSION` = `0.120.0` |
| Custom domain | Settings → **Domains** | `www.ctravel.top` |

## DNS

See `workspace/dev-builder/scripts/ctravel-dns-setup.md` in OpenClaw repo.

## Affiliate

Replace `AFFILIATE_*` placeholders in posts after Klook/Booking approval.
Template map: `workspace/ceo/templates/ctravel-affiliate-map.json`.
