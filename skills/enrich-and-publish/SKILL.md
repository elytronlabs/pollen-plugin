---
name: enrich-and-publish
description: Run Pollen's enrichment and publish the results to the store. Use when the user wants products enriched, asks Pollen to "do the work", wants to sync their catalog, or wants enriched data pushed to their store, Google or Meta.
---

Use the Pollen connector. Three steps, in order, each reported honestly.

1. Sync. If `get_account_summary` shows the last sync is old or products are missing, call `sync_catalog` first and wait for `get_pipeline_status` to show it finished.
2. Enrich. This is the paid step and the one that spends model calls. Before a catalog-wide run:
   - Tell the merchant how many products are pending or failed (from `get_account_summary` or `list_products`), that `enrich_all_products` processes exactly those (already-enriched products are not re-run), and that it runs in the background.
   - Get a yes. Then call `enrich_all_products`. For one product, `enrich_product` needs no such confirmation.
   - Poll `get_pipeline_status` at sensible intervals and report progress in counts, not adjectives.
3. Publish. When enrichment is done, call `write_back_to_store`. Explain what this writes: a separate data layer on each product (structured facts, agent description, search terms, schema) that agents read. The merchant's own titles and descriptions are never changed by this step.

Channels: Google Merchant Center and Meta catalogs are pushed by Pollen automatically once connected. If they are not connected, hand over to the channel-connect flow instead of pretending the data reached them.

Report at the end: products enriched, products published, and anything that failed with the reason Pollen gave. If a tool answers with `requiresUpgrade`, say which plan includes enrichment, once.
