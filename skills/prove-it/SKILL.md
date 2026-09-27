---
name: prove-it
description: Show evidence that AI agents actually see and cite a store. Use when the user asks whether AI is visiting their store, whether ChatGPT or Gemini mention them, wants the Deep Audit, or asks how they compare with similar stores.
---

Use the Pollen connector. This skill reports evidence. It never manufactures it.

1. Deep Audit: call `get_deep_audit`.
   - If the report exists, summarize: how many of the frozen shopper questions produced a citation of the store, with the evidence lines, and the catalog fix plan. Cited-or-not is the result; do not soften a zero.
   - If it is locked, say exactly what the report contains and how to unlock it (a one-time Deep Audit or a paid plan). Do not preview or estimate results.
2. Network comparison: call `get_network_insights`. Report the merchant's own figures next to the category benchmark. Where Pollen returns "not enough data" or a member-only marker, say that; a benchmark needs enough stores to exist and the comparison depth is part of Hive membership.
3. AI visits: the connector does not carry visit counts. They live in the Pollen dashboard's Traffic view (https://pollen.elytron.in). Point the merchant there and explain the two numbers they will see: crawl means an AI indexed the store; retrieve means an assistant fetched a page to answer a real shopper. Retrieve is the number that matters.

Rules: no fabricated traffic, revenue or "at risk" figures, no causal claims ("this fix caused that citation") beyond what the report itself states, and no promise of in-chat checkout. If the merchant asks "will this get me sales?", answer with what is measured and what is not.
