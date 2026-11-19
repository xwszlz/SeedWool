# SeedWool .com International · V3 (Strategy rebuild)

## Contents
- 12 public pages + 404: `index / substrate / rice / seedling / other / rockwool / yaas / standards / global / about / contact / verify / privacy / 404`
- `assets/css/tokens.css`: design tokens and all component styles (single file, no build)
- `assets/js/app.js`: rendering layer (share bar / products / batch verification / enquiry modal)
- `assets/data/*.json`: sectors / products / assets_ip / yaas / exports / route_map / indicators / batches
- `assets/img/`: WebP with JPEG fallback

## Deploy
1. Copy **all files** into the root of `xwszlz/SeedWool` (index.html must sit at root)
2. `git add . && git commit -m "..." && git push` → Vercel publishes automatically
3. Submit `https://www.seedwool.com/sitemap.xml` to Google Search Console

## Data updates (no HTML editing needed)
Product, sector and batch data live in `assets/data/*.json`.
Pages also inline a copy (`<script type="application/json">`) for first paint and SEO,
so either re-run the generator or edit the inline block — never change only one of the two.

### Non-negotiable data rules
- Only `ledger: A` counts toward the 140,000 t / CNY 2bn plan; `ledger: B` (building rockwool) is separate and **must never be summed**
- `target_vs_actual` is mandatory; 2029 capacity and revenue are always `target`
- Patent status: used under licence from the holder — **never phrase as "owned by the company"**
- Agricultural media and building insulation rockwool belong to different standard systems and cannot serve as acceptance criteria for each other
