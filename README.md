<p align="center">
  <img src="https://quote.nb8floral.com/static/nb8-logo-512.png" width="140" alt="NB8 Floral">
</p>

# NB8 Floral MCP Server

Find, price and order **wholesale artificial (silk) flowers** from AI assistants such as Claude,
ChatGPT, Cursor and VS Code — or ask what flowers are in a photo and where to buy them.

[NB8 Floral](https://nb8floral.com) is a manufacturer of artificial flowers that sells to
florists, wedding and event planners, and decorators. This is a hosted (remote) MCP server
backed by our live store data. **No account, API key or sign-in is needed.**

```
https://quote.nb8floral.com/mcp
```

Transport: Streamable HTTP · Authentication: none

[![Claude Directory](https://img.shields.io/badge/Claude-Connectors%20Directory-D97757)](https://claude.ai/directory/nb8-floral)

## Add it to your assistant

**Claude** — install from the
[Connectors Directory](https://claude.ai/directory/nb8-floral), or go to
Settings → Connectors → Add custom connector, paste the URL above and choose *No sign-in*.

**ChatGPT** — turn on developer mode (Settings → Apps & Connectors → Advanced), then create a
connector with the URL above and no authentication.

**Cursor / VS Code / other MCP clients** — add a remote server:

```json
{
  "mcpServers": {
    "nb8-floral": {
      "url": "https://quote.nb8floral.com/mcp"
    }
  }
}
```

## Tools

| Tool | What it does |
|---|---|
| `search_products` | Search by flower type, color and keywords. Returns price per pack, stems per pack, price per stem, delivery time, free-shipping flag, product link and photo. Can be limited to US-warehouse stock (about 7-day delivery). |
| `get_products` | Today's price, pack size and stock for specific products. |
| `identify_flowers` | Identify the flowers and colors in a photo (public image URL) and match each one to our products. Stem counts are approximate. |
| `create_checkout_link` | One-time link to a cart on nb8floral.com, pre-filled with the chosen products (rounded up to whole packs). Nothing is charged — you review and pay on our website. The link works once, within 30 minutes. |
| `create_quote_request` | Save a list for a quote (pre-order items, large or custom orders, shipping outside the contiguous US) and get an order code. |

Read-only tools: `search_products`, `get_products`, `identify_flowers`.
Write tools: `create_checkout_link`, `create_quote_request` (they create a cart or a quote list —
they never place an order or move money).

## Example prompts

- "Find white silk peonies from NB8 Floral that can arrive within a week."
- "I need about 200 burgundy rose stems for a wedding. What does NB8 charge per stem?"
- "What flowers are in this bouquet, and where can I buy them from NB8?" *(with an image link)*
- "Make me a checkout link for 60 stems of the white hydrangea."
- "I need yellow craspedia for an event on 20 December — request a quote from NB8."

## Good to know

- Prices are in USD **per pack**; each product shows how many stems are in a pack.
  No minimum order — one pack is enough.
- Online checkout ships to the contiguous United States (not Alaska or Hawaii), with free shipping.
  US-warehouse items arrive in about 7 days; other listed items ship from our factory in about 30 days.
- Pre-order items are made to order (about 45 days) and show an estimated price per stem or bunch;
  international shipping is quoted separately and they are ordered by quote.
- Photo identification is rate-limited per day.

## Privacy

The server receives only the arguments your assistant sends (search terms, product IDs,
quantities, and an image link if you use photo identification). It never sees your conversation
and keeps no IP addresses in its usage log. Details:
[privacy policy](https://quote.nb8floral.com/privacy#ai-assistants).

## Links

- Documentation: https://quote.nb8floral.com/ai
- Shop: https://nb8floral.com
- Support: nb8factory@gmail.com · WhatsApp +86 135 1875 9302

This repository holds the public description and registry metadata (`server.json`) for the
hosted server. The server itself runs on our infrastructure; there is nothing to install.

© Yiwu Shihe Trading Co., Ltd. (NB8 Floral)
