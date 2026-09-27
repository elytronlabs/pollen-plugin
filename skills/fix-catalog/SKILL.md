---
name: fix-catalog
description: Apply Pollen's automated catalog fixes or a per-product description. Use when the user wants to fix SEO titles, meta descriptions, tags, image alt text or brand, asks Pollen to "fix it", or wants to replace a product description with Pollen's version.
---

Use the Pollen connector. Every fix here writes to the merchant's live store, so confirm scope before each write.

Catalog-wide fixes:

1. Call `get_fix_opportunities` and show the counts per fix type: `seo`, `tags`, `altText`, `brand`.
2. Say plainly what each fix does and its rule: fill-only-empty. Pollen never overwrites a value the merchant wrote. Tell them which products will be touched.
3. Get an explicit yes for the fix type(s), then call `apply_fixes` once per type.
4. Fixes run on Pollen's worker. Call `get_pipeline_status` to report progress, and report what actually landed rather than what was requested.

Descriptions are different: never in bulk.

1. For one product, call `get_product` and show the `storefrontDescriptionCandidate` field, which is the exact text Pollen would publish. Do not show or offer the raw `agentDescription`; it is written for agents, not shoppers.
2. Only after the merchant approves that exact text, call `apply_description` for that one product.
3. Repeat per product. If they ask for "all descriptions", explain that Pollen replaces shopper-facing copy one product at a time, on approval, and offer to go product by product.

Facts only the merchant knows (SKU, barcode, weight, brand): when they give values in conversation ("all tees weigh 180 grams"), call `update_product_facts` with the products they mean, and confirm the list before writing.

If a tool answers with `requiresUpgrade`: say which plan includes this fix and what else it includes, once, in two sentences. Do not repeat the pitch.
