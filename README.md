# SeedWool seedwool.com static site

## Deploy to Vercel
1. Copy all files in this folder to the root of `xwszlz/SeedWool` (master), with index.html at root.
2. `git add . && git commit -m "site: SeedWool UI v2" && git push origin master`.
3. Vercel publishes automatically (static, no build command). Point `seedwool.com` to the project.
4. Submit `https://seedwool.com/sitemap.xml` to Google Search Console.

## Content
- Products/indicators/batches/papers: edit JSON files under `assets/data/`.
- `assets/js/data-adapter.js` is the data abstraction layer — switch `DataSource` to an API later without touching pages.
- All indicators are engineering-illustrative values; do not present them as certified test results.

## Inquiry
- All CTAs open an email dialog to 1207560536@qq.com. No online form, no QR code, no pricing.
