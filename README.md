# vdhout.cc

Static landing page served from **Cloudflare Pages** on the apex domain `vdhout.cc`.

## Deploy

```bash
set -a; source ~/.cloudflare/keys; set +a
export CLOUDFLARE_API_TOKEN="$CF_PAGES_TOKEN"
export CLOUDFLARE_ACCOUNT_ID="$CF_ACCOUNT_ID"
npx wrangler pages deploy . --project-name=vdhout-cc --branch=main --commit-dirty=true
```

Pushen naar `main` triggert geen auto-deploy (geen Git-koppeling). Voor auto-deploy: in CF dashboard onder Pages → vdhout-cc → Settings → Builds & deployments → koppel de GitHub repo.

## DNS

Apex `vdhout.cc` is een proxied CNAME naar `vdhout-cc.pages.dev` (Cloudflare CNAME flattening). Geen handmatige A-records nodig.

## Local preview

```bash
python3 -m http.server 8000
```
