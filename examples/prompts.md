# StoreInspect MCP example prompts

These prompts are starting points for StoreInspect MCP clients. Ask the client to call `list_taxonomy` before guessing filter values.

## Find qualified Shopify stores

```text
Use StoreInspect to find up to 25 US beauty stores with 50K+ monthly traffic that use Meta Pixel but do not use Klaviyo. Show the domain, traffic tier, detected apps and pixels, and contact availability.
```

## Find prospects missing an app

```text
Use StoreInspect to find Shopify stores in food and beverage that have meaningful traffic but do not use an age-verification app. First check the taxonomy for supported categories and app names.
```

## Enrich known accounts

```text
Use StoreInspect to enrich allbirds.com, gymshark.com, and tentree.com. Compare their themes, apps, pixels, traffic tiers, revenue tiers, and contact availability in a table.
```

## Preview decision-makers

```text
Use StoreInspect to search for founder, CEO, ecommerce, or marketing decision-makers at these domains. Return masked previews and contact IDs only. Do not reveal contact channels.
```

## Reveal selected contacts

Reveals can spend contact credits. Replace the example IDs with IDs returned by `search_shopify_contacts` and confirm the exact selection before asking the client to reveal them.

```text
Reveal these StoreInspect contact IDs: ct_example_one and ct_example_two. I confirm spending credits for exactly these contacts.
```

## Check usage first

```text
Use StoreInspect to show my current plan, API quota, search-row usage, and remaining contact credits before running a search.
```
