---
description: Orientation for the Pollen plugin. Connect your store and see what to run first.
---

Give the merchant a short orientation for Pollen, then act on their answer.

1. Check whether the Pollen connector is connected by calling `get_account_summary`. If it fails with an authentication error, tell them to connect Pollen from this plugin's Connectors tab and sign in with their Pollen account (a free account with a connected Shopify or WooCommerce store is enough: https://pollen.elytron.in). Stop there until it works.
2. If it works, report in three lines: which store this is, the current plan, and the agent-readiness figure with the product count. Plain language, no protocol names.
3. Offer exactly three next steps, matched to their state:
   - Nothing enriched yet: "see what agents currently read from your store" (store readiness), then "enrich and publish".
   - Enriched but gaps remain: "fix what Pollen can fix", then "connect Google or Meta".
   - Already live on channels: "check the proof" (AI visits, Deep Audit).
4. Wait for their choice. Do not start any paid or catalog-wide action from this orientation.
