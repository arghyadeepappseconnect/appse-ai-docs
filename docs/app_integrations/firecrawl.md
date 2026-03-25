---
title: "Firecrawl"
slug: /app-integrations/firecrawl/
---

Firecrawl is a powerful web data API built for AI agents and workflows. It turns entire websites into clean, LLM-ready markdown or structured data. Integrating Firecrawl into appse ai enables you to scrape, crawl, search, extract, and map websites at scale with a single API.

---

## Set Up Credential

:::info

Before you create a credential for Firecrawl using appse ai, ensure you have a Firecrawl account and have generated an API key from the Firecrawl dashboard.

:::

### Required Fields

You'll be asked to fill in the following details:

| Field           | Description                                        |
| --------------- | -------------------------------------------------- |
| Connection Name | A name to help you identify this connection        |
| API Key         | Your API Key from the Firecrawl dashboard          |

---

### Step-by-Step Guide

#### 1. Open the Credential Form

Click **Select a Credential** and choose **Firecrawl** from the application list.

<img src="/img/credentials/firecrawl/firecrawl-create-new-connection.png" alt="appse ai Firecrawl Select Credential" width="700"/>

<br/>

This opens the Firecrawl credential form. Add your **Connection Name**.

<img src="/img/credentials/firecrawl/firecrawl-connection-name.png" alt="appse ai Firecrawl Connection Name" width="700"/>

#### 2. Sign In to the Firecrawl Dashboard

Go to [Firecrawl](https://www.firecrawl.dev/app) and sign in with your account. You can sign up for free — no credit card required.

#### 3. Get Your API Key

After logging in, navigate to **API Keys** from the left sidebar of your dashboard.

<img src="/img/credentials/firecrawl/firecrawl-api-key-create.png" alt="appse ai Firecrawl Get API Key" width="700"/>
Generate a new API key and copy it. Your key will start with `fc-`.
<img src="/img/credentials/firecrawl/firecrawl-api-key-name.png" alt="appse ai Firecrawl API Key Name" width="700"/>

#### 4. Paste API Key in appse ai

Return to the appse ai credential form. Paste the copied API key into the **API Key** field and click **"Save"** to store and validate your credential.

<img src="/img/credentials/firecrawl/firecrawl-paste-api-key.png" alt="appse ai Firecrawl Save Credential" width="700"/>

<br/>

:::warning

Keep your API key secure. Do not share it publicly. If you suspect your key has been compromised, you can regenerate or delete it from the Firecrawl dashboard at any time.

:::

---

## Triggers and Actions

Here is a list of the available actions for Firecrawl:

### Actions

- **Scrape Website** — Scrape a single URL and retrieve its full content as clean markdown, HTML, or structured data. Ideal for extracting complete information from a specific web page.

- **Crawl Website** — Crawl an entire website starting from a given URL. Firecrawl follows internal links and retrieves content across all accessible sub-pages.

- **Get Crawl Status** — Check the status of an ongoing or completed crawl job. Requires a **Crawl Job ID** returned from the Crawl Website action.

- **Extract Website** — Extract specific, structured data from a URL using an AI-powered prompt. Returns only the content you need — such as prices, headlines, or contact details — in clean JSON format.

- **Get Extract Status** — Check the status of an ongoing or completed extract job. Requires an **Extract Job ID** returned from the Extract Website action.

- **Search Website** — Search the web and get full page content from the results in a single call. Returns relevant URLs along with their scraped content.

- **Website Map** — Generate a structured map of all URLs found on a website. Useful for discovering the complete link structure of a site before crawling or scraping.

- **Make API Call** — Make a custom API call to any Firecrawl endpoint. Useful for advanced use cases not covered by the standard actions.

---

## Support

Need help? Contact our support team at [hello@appse.ai](mailto:hello@appse.ai)