# vdhout.cc

Static landing page (a hand-set index of the vdhout-tools) op het apex-domein
`vdhout.cc`. Het is een **static-assets Cloudflare Worker** (`name = "vdhout-cc"`,
alleen `[assets]`, geen server-script), niet Cloudflare Pages.

## Deploy

Pushen naar `main` deployt automatisch via de Git-koppeling (Workers Builds).
Voor een handmatige deploy:

```bash
set -a; source ~/.cloudflare/keys; set +a
export CLOUDFLARE_API_TOKEN="$CF_WORKERS_TOKEN"
export CLOUDFLARE_ACCOUNT_ID="$CF_ACCOUNT_ID"
npx wrangler deploy
```

## DNS / custom domain

Het apex-domein `vdhout.cc` is als custom domain aan deze Worker gekoppeld via
de account-level Workers Domains API (net als de andere tools, zie de comment in
`wrangler.toml`), niet via een `[[routes]]`-entry. Het geproxyde DNS-record
wordt daarbij automatisch aangemaakt.

## Local preview

```bash
python3 -m http.server 8000
```
