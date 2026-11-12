# Rickie Reilly's website

GitHub Pages source for `rickiereilly.com`, including the SpaceX valuation model
at `/spacex/`. No application server or build step is required.

## Layout and local preview

- `docs/index.html`: homepage.
- `docs/spacex/index.html`: uploaded model, initially preserved byte for byte.
- `docs/home/` and `docs/spacex-5-10-year-model/`: legacy URL redirects.
- `.agents/skills/update-site/SKILL.md`: reusable agent maintenance procedure.

Run `python -m http.server 8000 --directory docs` from the repository root and
open `http://localhost:8000/` and `http://localhost:8000/spacex/`.

The model loads Tailwind CSS, Chart.js, and Google Fonts from external CDNs.
Its calculations run in the visitor's browser; there is no live financial feed.

## Publishing

Repository: `reillz10/reillz10.github.io`.
Pages source: branch `main`, directory `/docs`.
Before domain cutover: `https://reillz10.github.io/` and
`https://reillz10.github.io/spacex/`.
Publishing main triggers GitHub Pages. Check the Pages deployment before
reporting success. Revert a commit to undo a change.

## Custom domain cutover (pending)

The current Google Sites homepage stays live until DNS is changed. Do not add a
Pages custom domain until the GitHub address has been tested and domain access
is available. Set the Pages domain to `rickiereilly.com` and create
`docs/CNAME` containing that domain. Follow GitHub's current custom-domain
instructions and verify domain ownership in GitHub before changing DNS.

Typical apex A records for GitHub Pages:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

The `www` CNAME should target `reillz10.github.io`. Inspect existing A, AAAA,
CNAME and forwarding records for conflicting website targets. Preserve MX,
TXT, and other unrelated records. Once GitHub provisions the certificate,
enable HTTPS and verify the apex, www, homepage, model, and legacy redirects.

DNS cannot route a URL path to another host. Both the homepage and `/spacex/`
will be served by this repository after cutover.
