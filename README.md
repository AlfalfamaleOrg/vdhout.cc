# vdhout.cc

Static landing page served from GitHub Pages on the apex domain `vdhout.cc`.

## DNS

Point the apex domain at GitHub Pages with these `A` records (IPv4) and the matching `AAAA` records (IPv6):

```
A    185.199.108.153
A    185.199.109.153
A    185.199.110.153
A    185.199.111.153

AAAA 2606:50c0:8000::153
AAAA 2606:50c0:8001::153
AAAA 2606:50c0:8002::153
AAAA 2606:50c0:8003::153
```

(Optional) For `www.vdhout.cc`, add a `CNAME` record pointing at `alfalfamaleorg.github.io.`.

## Local preview

Open `index.html` in a browser, or:

```
python3 -m http.server 8000
```
