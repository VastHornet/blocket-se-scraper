[Blocket Se Scraper](https://apify.com/santamaria-automations/blocket-se-scraper?fpr=data)

# Blocket.se Scraper

Scrape classified listings from [blocket.se](https://www.blocket.se), Sweden's largest online marketplace (Schibsted group).

## How it works

1. Go to [blocket.se](https://www.blocket.se) and set up your search with all desired filters (category, price, brand, transmission, location, etc.)
2. Copy the URL from your browser
3. Paste it into the **Search URLs** input
4. Run the actor

The actor extracts all listings matching your search, with automatic pagination.

## Use with AI Agents (MCP)

Connect this actor to any MCP-compatible AI client — Claude Desktop, Claude.ai, Cursor, VS Code, LangChain, LlamaIndex, or custom agents.

**Apify MCP server URL:**

```
https://mcp.apify.com?tools=santamaria-automations/blocket-se-scraper
```

**Example prompt once connected:**

> "Use `blocket-se-scraper` to scrape company data from blocket se. Return results as a table."

Clients that support dynamic tool discovery (Claude.ai, VS Code) will receive the full input schema automatically via `add-actor`.

## Features

- **Any filter combination** -- Whatever you can filter on blocket.se, the actor can scrape
- **Multiple searches** -- Paste multiple URLs to run several searches in one run
- **Detail enrichment** -- Optionally get full description, condition, and brand info
- **Rich SERP data** -- Title, price, location, GPS coordinates, images already from search results
- **Fast & cheap** -- HTTP-only, 128 MB, pay-per-result

## Output

| Field | Description | Source |
| --- | --- | --- |
| `title` | Listing title | Search |
| `price` / `currency` | Price in SEK | Search |
| `location` | City/area | Search |
| `latitude` / `longitude` | GPS coordinates | Search |
| `brand` | Product brand | Search |
| `image_url` / `image_urls` | Images | Search |
| `description` | Full listing description | Detail |
| `condition` | Item condition (New/Used/etc.) | Detail |
| `category` | Category path | Detail |
| `posted_at` | Publication date (ISO 8601) | Search |
| `source_url` | Link to listing on blocket.se | Both |

## Pricing

No start fee -- pay only for results:

| Event | Cost |
| --- | --- |
| Listing (basic) | $0.003 |
| Listing (with details) | $0.005 |

**100 listings = $0.30** (basic) or **$0.50** (with details)

## Examples

### Cars under 330K SEK with automatic transmission

```
{
  "searchUrls": ["https://www.blocket.se/mobility/search/car?price_to=330000&transmission=1&variant=0.749"],
  "maxResults": 50
}
```

### Multiple searches in one run

```
{
  "searchUrls": [
    "https://www.blocket.se/recommerce/forsale/search?q=iphone",
    "https://www.blocket.se/recommerce/forsale/search?q=macbook",
    "https://www.blocket.se/mobility/search/car?price_to=100000"
  ],
  "maxResults": 200,
  "maxResultsPerQuery": 80
}
```

### With full details

```
{
  "searchUrls": ["https://www.blocket.se/recommerce/forsale/search?q=cykel"],
  "maxResults": 100,
  "includeDetails": true
}
```

## Related Actors

**European Classifieds**

- [Finn.no Scraper — Norway](https://apify.com/santamaria-automations/finn-no-scraper)
- [DBA.dk Scraper — Denmark](https://apify.com/santamaria-automations/dba-dk-scraper)
- [Tori.fi Scraper — Finland](https://apify.com/santamaria-automations/tori-fi-scraper)
- [Marktplaats.nl Scraper — Netherlands](https://apify.com/santamaria-automations/marktplaats-nl-scraper)
- [Kleinanzeigen.de Scraper — Germany](https://apify.com/santamaria-automations/kleinanzeigen-de-scraper)

**Real Estate**

- [Homegate.ch Scraper — Swiss real estate](https://apify.com/santamaria-automations/homegate-scraper)
- [Immowelt.de Scraper — German real estate](https://apify.com/santamaria-automations/immowelt-de-scraper)

**Enrich your data**

- [Website Email & Phone Scraper](https://apify.com/santamaria-automations/website-email-scraper)
- [Google Maps Scraper](https://apify.com/santamaria-automations/google-maps-scraper)
- [Website Contact Extractor](https://apify.com/santamaria-automations/website-contact-extractor)

## Issues & Feedback

Missing something or not working as expected? [Open an issue](https://console.apify.com/actors/xo9X4b8qC1rNclJH4/issues) and we'll fix it.