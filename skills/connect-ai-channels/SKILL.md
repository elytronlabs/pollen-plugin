---
name: connect-ai-channels
description: Connect a store to Google Merchant Center or Meta catalogs through Pollen. Use when the user wants their products on Google, Gemini, Google Shopping, Facebook, Instagram or Meta AI, asks to "connect Google" or "connect Meta", or a connection is stuck.
---

Use the Pollen connector. These are state machines. Read the status first, act on the state, and only the merchant clicks consent.

Google:

1. Call `get_google_connect_status`. Act on `status`:
   - `none`: call `connect_google`. It returns an `authUrl`. Give the merchant that link to open themselves and grant Google consent. You cannot open it. Then check status again.
   - `selecting_account`: show the candidate accounts returned and ask which one. Call `pick_google_account` with their choice.
   - `tos_required`: show the `termsUrl`. Only after they say they accept, call `accept_google_terms`.
   - `verifying`, `awaiting_approval`, `connector_pending`: Pollen is working or Google is reviewing. Say what is happening and that no action is needed; check back later.
   - `active`: connected. Products flow automatically after enrichment.
2. Never pick an account or accept terms on the merchant's behalf.

Meta (Facebook and Instagram):

1. Call `get_meta_connect_status`. Act on `status`:
   - `none`: call `connect_meta`, hand the merchant the `authUrl` to approve via Facebook Login, then check status.
   - `selecting_business`: show candidates, call `pick_meta_business` with their choice.
   - `selecting_catalog`: show the candidate catalogs with their product counts. Never pick an existing catalog without the merchant's explicit choice; offer `__create__` for a fresh Pollen-managed catalog if they are unsure.
   - other states: explain in one line and what is needed next.

Access: these channels are on the Autopilot plan. If a tool answers with `requiresUpgrade`, say so once and offer what is available now.

When something needs the merchant's hands, give one clear instruction, not a list.
