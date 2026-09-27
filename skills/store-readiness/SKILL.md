---
name: store-readiness
description: Explain how ready a merchant's store is for AI shopping agents. Use when the user asks where their store stands, what their score means, why AI assistants don't recommend them, or which products are weakest.
---

Use the Pollen connector. Read first, never change anything in this skill.

1. Call `get_account_summary` for the plan, agent-ready figure, product counts and last sync, enrichment and publish times.
2. Call `get_fix_opportunities` for the score breakdown: points lost per dimension, what Pollen can fix automatically, and the "needs you" list.
3. If the user names a product or asks for the weakest ones, call `list_products` (sort by lowest score) and `get_product` for detail.

How to report:

- Lead with one sentence a store owner understands: can AI assistants read this catalog today, and how much of it. Say "catalog strength" or "readiness", not protocol names.
- Name the three gaps that cost the most points, each with what fixes it and who does it: Pollen automatically, the merchant (facts only they know, such as barcodes and weights), or a paid plan step.
- Distinguish enriched from not enriched. Un-enriched products score low because nothing has read them yet, not because the data is bad.
- Never invent revenue, "sales at risk" or traffic figures. Pollen does not compute them and neither should you. If a number is not in a tool response, do not state it.
- Free tier: the audit is complete and uncapped. Enrichment, fixes and publishing need a paid plan. Say what each unlocks in one line, without pressure.

End by offering the next concrete step: run the fixes, enrich, or connect a channel.
