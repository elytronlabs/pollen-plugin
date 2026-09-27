# Pollen

Run your store's AI readiness from Claude.

AI assistants like ChatGPT, Gemini, Claude and Perplexity now recommend products to shoppers, but only from stores they can actually read. Pollen makes a Shopify or WooCommerce catalog readable, recommendable and, where the rails exist, buyable by AI agents. This plugin lets you run all of it from a conversation.

## What you can do

- **See where you stand.** Your agent-readiness score, which channels your store is live on, and exactly which gaps cost you points.
- **Fix what Pollen can fix.** Empty SEO titles and descriptions, thin tags, missing image alt text, missing brand. Fill-only-empty: values you wrote yourself are never overwritten.
- **Enrich and publish.** Pollen reads each product's text and photos, extracts the structured facts agents ask for, and writes them back to your store as a separate data layer. Your titles and descriptions stay yours.
- **Connect AI channels.** Google Merchant Center and Meta catalogs, with Claude walking you through the two consent clicks only you can make.
- **Check the proof.** Real AI-crawler and AI-referral visits to your store, and the Deep Audit: real shopper questions asked to real assistants, cited or not, with evidence.

## How to use it

1. Install the plugin, then connect the Pollen connector from the plugin's Connectors tab and sign in. You need a Pollen account with a connected store: start at https://pollen.elytron.in. The free tier includes the readiness audit; enrichment, fixes and publishing are on paid plans.
2. Ask in plain language: "where does my store stand?", "what should I fix first?", "enrich my catalog and publish it", "connect Google", "is any AI actually visiting my store?"
3. Type `/pollen-ai:start` for a short orientation.

## What data goes where

Everything runs through the Pollen connector at `https://pollen.elytron.in/mcp`, authenticated with your own Pollen account through OAuth. Claude reads your product catalog, readiness scores, pipeline status and AI-visit analytics from Pollen, and, only when you ask, triggers enrichment, fixes and publishing that Pollen writes to your own store. No API keys are stored in this plugin. No customer or order data is read. Terms: https://pollen.elytron.in/terms. Privacy: https://pollen.elytron.in/privacy.

Made by Elytron Labs. Support: hello@elytron.in
