# VK Scraper: Vk Scraper API for Python & Node.js (2026)

Scrape public VK (VKontakte) wall posts with likes, reposts, views, media and comments from any community or profile. No login needed. JSON, CSV, Excel.

**[▶ Try the VK Scraper free on Scrapely](https://scrape.ly/store/echofield/vk-scraper)** · [Compare Scrapely vs other scraping tools](https://scrape.ly/compare)

This repository shows how to scrape Vk data with the [VK Scraper](https://scrape.ly/store/echofield/vk-scraper) using the official
**Scrapely SDKs for JavaScript and Python**. You pass the input, Scrapely runs the vk scraper in the cloud
(proxies, retries, browser and scaling included) and returns clean, structured data as JSON, CSV or Excel.
No scraper code to maintain and no blocked requests to debug.

## Why use this Vk scraper

- **No-code or API:** run it from the [Scrapely Store](https://scrape.ly/store/echofield/vk-scraper) or from your code with the SDK.
- **Structured vk data:** ready-to-use fields instead of raw HTML.
- **Pay per result:** $3.60 per 1,000 vk post results, no monthly subscription required.
- **Maintained and monitored:** scrapers are tested around the clock and fixed fast when Vk changes.
- **Integrations:** n8n, Make, Zapier, LangChain, LlamaIndex, MCP (Claude, Cursor) and webhooks.

## What Vk data can you extract?

Scrape public VK (VKontakte) wall posts with likes, reposts, views, media and comments from any community or profile. No login needed. JSON, CSV, Excel.

## Quick start

1. [Sign up for Scrapely](https://scrape.ly) (free plan available) and copy your API token from
   **Settings → API & Integrations**.
2. Clone this repo and set your token:

```bash
export SCRAPELY_TOKEN=your_token
```

### Node.js (JavaScript SDK)

```bash
npm install
node example.js
```

```js
const { ScrapelyClient } = require('scrapely-client');
const client = new ScrapelyClient({ token: process.env.SCRAPELY_TOKEN });

const run = await client.actor('echofield/vk-scraper').call({"targets": ["kinopoisk", "rbc"], "maxItems": 20, "proxyConfiguration": {"useScrapelyProxy": true, "scrapelyProxyGroups": ["DATACENTER"]}});
const { items } = await client.dataset(run.defaultDatasetId).listItems();
```

### Python (Python SDK)

```bash
pip install -r requirements.txt
python example.py
```

```python
from scrapely_client import ScrapelyClient
client = ScrapelyClient(os.environ['SCRAPELY_TOKEN'])

run = client.actor('echofield/vk-scraper').call(run_input={ "targets": [ "kinopoisk", "rbc" ], "maxItems": 20, "proxyConfiguration": { "useScrapelyProxy": True, "scrapelyProxyGroups": [ "DATACENTER" ] } })
items = list(client.dataset(run.default_dataset_id).iterate_items())
```

### REST API / cURL

```bash
curl -X POST "https://api.scrape.ly/v2/acts/echofield~vk-scraper/run-sync-get-dataset-items?token=$SCRAPELY_TOKEN" \
  -H "Content-Type: application/json" \
  -d @input.json
```

## Example input

```json
{
  "targets": [
    "kinopoisk",
    "rbc"
  ],
  "maxItems": 20,
  "proxyConfiguration": {
    "useScrapelyProxy": true,
    "scrapelyProxyGroups": [
      "DATACENTER"
    ]
  }
}
```

See every input option on the [VK Scraper page](https://scrape.ly/store/echofield/vk-scraper).

## Pricing

**$3.60 per 1,000 vk post results.** Free plan available, no credit card needed to start. Check current pricing on the
[Store page](https://scrape.ly/store/echofield/vk-scraper) and see how Scrapely compares with other tools on [scrape.ly/compare](https://scrape.ly/compare).

## FAQ

**How do I scrape Vk with Python?** Install `scrapely-client-python`, set `SCRAPELY_TOKEN` and run
`example.py`. The scraper runs on Scrapely and you read the results from the dataset.

**How do I scrape Vk with Node.js?** Install `scrapely-client`, set `SCRAPELY_TOKEN` and run `example.js`.

**Is there a vk scraper API?** Yes. Call `POST https://api.scrape.ly/v2/acts/echofield~vk-scraper/runs`
or use `run-sync-get-dataset-items` to get results in one request.

**Do I need proxies?** No. Proxies, retries and browsers are handled by Scrapely.

**Is scraping Vk legal?** This scraper collects publicly available data. Check Vk's terms and the
laws that apply to you, especially for personal data (GDPR, CCPA).

**Can I schedule it or get results by webhook?** Yes. Use Scrapely schedules and webhooks, or n8n, Make and Zapier.

## Looking for an alternative?

Scrapely is an alternative to Apify, Bright Data, ScraperAPI, Firecrawl, Octoparse, PhantomBuster, SerpApi,
Zyte and others. See the side-by-side pricing on [scrape.ly/compare](https://scrape.ly/compare).

---

**Keywords:** vk scraper, vk scraper, vk scraper api, vk scraper python, vk scraper node.js,
scrape vk, vk data extraction, vk crawler, vk api, export vk data to csv, vk-scraper

License: MIT. Example code only; the scraper runs on [Scrapely](https://scrape.ly/store/echofield/vk-scraper).
