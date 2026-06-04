[Blocket Se Scraper](https://apify.com/logiover/blocket-se-scraper?fpr=data)

# 🇸🇪 Blocket.se Scraper — Sweden's Largest Classifieds Platform

Extract listings from **[Blocket.se](https://www.blocket.se)** — Sweden's #1 classified ads platform, founded in 1996 and used by millions of Swedes every month. Scrape marketplace items, vehicles, real estate and job postings across all Swedish regions — with prices, images, descriptions, seller details and category-specific attributes.

Blocket.se has over **1 million active listings** at any time across all categories, from Stockholm apartments to Volvo cars in Gothenburg. This scraper uses Blocket's internal search API (`search_bff`) for fast, structured, complete data extraction.

---

## 🔍 What can you scrape?

| Category | Input value | Description |
| --- | --- | --- |
| 🛍️ All categories | `` (empty) | Everything on Blocket |
| 🚗 Vehicles | `1020` | Cars, motorcycles, boats, caravans |
| 🏠 Real Estate | `5040` | Apartments, houses, rentals |
| 📱 Electronics | `1010` | Phones, computers, gaming |
| 🎿 Leisure & Hobby | `4040` | Sports, music, collectibles |
| 🏠 Home & Household | `3020` | Furniture, appliances, garden |
| 💼 Jobs | `6020` | Job listings |
| 👗 Fashion | `3010` | Clothing, shoes, accessories |
| 🏢 Business | `2010` | Business-related ads |

---

## 🌍 Swedish regions

Filter by any of 21 Swedish regions using the `location` field:

| Region | Location value |
| --- | --- |
| Hela Sverige (All Sweden) | `` (empty) |
| Stockholm | `12` |
| Västra Götaland (Gothenburg) | `19` |
| Skåne (Malmö) | `11` |
| Uppsala | `14` |
| Östergötland | `21` |
| Dalarna | `2` |
| Norrbotten | `10` |

---

## 💡 Use cases

**Marketplace & E-commerce**

- Price monitoring and comparison for second-hand goods across Sweden
- Arbitrage opportunity detection between Blocket and other platforms
- Brand presence analysis — track which products sell fastest and at what price
- Build price alert tools for specific items or categories
- AI training datasets with Swedish-language product descriptions

**Vehicles**

- Build Swedish used car valuation tools with real market data
- Track Volvo, SAAB, BMW pricing trends by model, year and mileage
- Monitor dealer vs private seller price differences
- Competitive intelligence for Swedish car dealerships

**Real Estate**

- Monitor rental and purchase prices across Stockholm, Gothenburg and Malmö
- Track price per m² trends in Swedish cities
- Build automated property alerts for specific budgets and sizes
- Generate leads for real estate agencies and brokers

**Jobs & Business Intelligence**

- Track Swedish labour market trends and hiring activity by region
- Monitor demand for specific skills and roles
- Generate datasets for salary benchmarking in Sweden

---

## 📦 Output fields

### Common fields (all categories)

| Field | Description | Example |
| --- | --- | --- |
| `id` | Unique Blocket listing ID | `"1401053984"` |
| `url` | Full listing URL | `"https://www.blocket.se/annons/..."` |
| `title` | Listing headline | `"iPhone 15 Pro 256GB Svart"` |
| `price` | Asking price in SEK | `"8 500 kr"` |
| `location` | City and region | `"Stockholm, Stockholms län"` |
| `category` | Blocket category name | `"Mobiltelefoner"` |
| `sellerName` | Seller or dealer name | `"Erik Johansson"` |
| `sellerType` | Privat or Företag | `"Privat"` |
| `imageUrl` | Cover photo URL | `"https://img.blocket.se/..."` |
| `imageUrls` | All photos comma-separated | `"url1, url2, url3"` |
| `description` | Ad description (first 500 chars) | `"Säljer min iPhone..."` |
| `publishedAt` | Publication timestamp | `"2026-03-16T10:32:00+02:00"` |
| `scrapedAt` | Scrape timestamp | `"2026-03-17T09:42:46.272Z"` |

### 🚗 Vehicles (Fordon)

| Field | Description | Example |
| --- | --- | --- |
| `make` | Vehicle brand | `"Volvo"` |
| `model` | Vehicle model | `"V70"` |
| `year` | Model year | `"2018"` |
| `mileage` | Odometer in mil (1 mil = 10 km) | `"8 500 mil"` |
| `fuel` | Fuel type | `"Bensin"` / `"Diesel"` / `"El"` |
| `gearbox` | Transmission | `"Automat"` / `"Manuell"` |
| `color` | Exterior color | `"Svart"` |
| `condition` | Condition | `"Begagnad"` |

### 🏠 Real Estate (Bostad)

| Field | Description | Example |
| --- | --- | --- |
| `size` | Living area in m² | `"72 m²"` |
| `rooms` | Number of rooms | `"3 rum"` |
| `rent` | Monthly rent | `"8 500 kr/mån"` |

---

## ⚙️ Input options

### Search all of Sweden

```
{
  "searchQuery": "iPhone",
  "category": "",
  "location": "",
  "maxResults": 100,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

### Search vehicles in Stockholm

```
{
  "searchQuery": "Volvo",
  "category": "1020",
  "location": "12",
  "maxResults": 100,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

### All listings in Gothenburg

```
{
  "searchQuery": "",
  "category": "",
  "location": "19",
  "maxResults": 200,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

### Real estate listings

```
{
  "searchQuery": "",
  "category": "5040",
  "location": "",
  "maxResults": 100,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

### Unlimited — full category export

```
{
  "searchQuery": "",
  "category": "1020",
  "location": "",
  "maxResults": 0,
  "proxyConfiguration": { "useApifyProxy": true }
}
```

---

## 📊 Sample output

```
{
  "id": "1401053984",
  "url": "https://www.blocket.se/annons/1401053984",
  "title": "Volkswagen Golf 1.4 TSI Highline",
  "price": "89 000 kr",
  "location": "Stockholm, Stockholms län",
  "category": "Personbilar",
  "sellerName": "Stefan Johansson",
  "sellerType": "Privat",
  "make": "Volkswagen",
  "model": "Golf",
  "year": "2018",
  "mileage": "6 500 mil",
  "fuel": "Bensin",
  "gearbox": "Manuell",
  "color": "Vit",
  "imageUrl": "https://img.blocket.se/...",
  "publishedAt": "2026-03-15T14:22:00+02:00",
  "scrapedAt": "2026-03-17T11:42:46.272Z"
}
```

---

## 💰 Pricing

| Volume | Estimated cost |
| --- | --- |
| 100 listings | ~$0.50 |
| 500 listings | ~$2.50 |
| 1,000 listings | ~$5.00 |
| 10,000 listings | ~$50.00 |

| Tier | Price per result |
| --- | --- |
| Default | $0.005 |
| Bronze | $0.0045 |
| Silver | $0.004 |
| Gold | $0.0035 |

---

## ⚡ Performance

- **search_bff API** — Blocket's internal search API, 40 listings per page
- **2-step flow** — fetch HTML to get auth token, then call JSON API
- **Automatic pagination** — follows all pages up to `maxResults`
- **Deduplication** — each listing saved exactly once
- **10 retries per request** — handles temporary blocks automatically

---

## 🔒 Proxy usage

Blocket.se uses bot detection for high-volume requests. Apify's residential proxy pool is recommended for stable access. The scraper automatically extracts the required authentication token from the HTML page before calling the JSON API.

---

## ❓ FAQ

**How large is Blocket.se?**

Blocket.se is Sweden's largest and oldest classifieds platform, founded in 1996. It has millions of monthly users and over 1 million active listings across all categories including cars, real estate, electronics, fashion and jobs.

**What language are the listings in?**

Swedish. All titles, descriptions and attribute values appear in Swedish as shown on blocket.se.

**What is "mil" in mileage?**

Swedish vehicles use "mil" (Swedish mile = 10 km) for odometer readings. So "8 500 mil" = 85,000 km.

**Can I filter by specific car make or model?**

Use the `searchQuery` field with the make/model name (e.g. `"Volvo V70"`) combined with `category: "1020"` for vehicles.

**Is scraping Blocket.se legal?**

This scraper collects publicly available listing data visible to any website visitor without login. Always use data responsibly and in compliance with applicable laws in your jurisdiction.