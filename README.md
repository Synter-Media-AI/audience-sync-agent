# Audience Sync MCP Starter Kit — Sync Audiences Across All Ad Platforms

[![MCP Compatible](https://img.shields.io/badge/MCP-compatible-blue)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform: Multi-Platform](https://img.shields.io/badge/Platform-Audience%20Sync-8B5CF6)](https://syntermedia.ai)

**Upload your email list to every ad platform in one command.** Open this repo in Amp, Cursor, or VS Code and sync Customer Match, Custom Audiences, and Matched Audiences across Google, Meta, LinkedIn, TikTok, X, Reddit, and Amazon — all at once.

---

## Why Audience Sync?

First-party data is the most valuable targeting signal in digital advertising. Your customer email list, when uploaded as a Custom Audience, lets ad platforms find your exact customers and build Lookalike audiences to find more people like them.

The problem? Every platform has a different audience upload format, different hashing requirements, different API endpoints, and different field mappings. Uploading a 10,000-email list to 5 platforms manually takes 2+ hours of tedious work. And audiences go stale — you need to refresh monthly.

An AI agent turns a 2-hour task into a single command. "Upload my customer list to all platforms" handles formatting, SHA-256 hashing, API uploads, and Lookalike creation across every connected platform.

**Best for:** Remarketing, first-party data activation, suppression lists, lookalike audience building, anyone who advertises on multiple platforms.

---

## Quick Start (30 Seconds)

### Amp / Cursor / VS Code (Copilot)

1. **Get a free API key** at [syntermedia.ai/developer](https://syntermedia.ai/developer)
2. **Set the key:**
   ```bash
   export SYNTER_API_KEY=syn_your_key_here
   ```
3. **Open this repo** in your editor
4. **Start chatting** — MCP tools are pre-configured in `.mcp.json`

### Claude Desktop

Copy `claude_desktop_config.json` to your Claude config directory and replace the API key:

- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`

---

## What You Can Do

| Capability | Example |
|-----------|---------|
| **Upload to All Platforms** | "Sync my customer email list to Google, Meta, LinkedIn, and TikTok" |
| **Lookalike Creation** | "Create a 1% Lookalike on Meta from my top customers" |
| **Suppression Lists** | "Add my full customer list as an exclusion on all acquisition campaigns" |
| **Segment-Based Audiences** | "Upload VIP customers to Meta, trial users to Google" |
| **Audience Refresh** | "Refresh all audiences with the latest CRM data" |
| **Match Rate Reports** | "What's the match rate for my email list on each platform?" |
| **Cross-Platform Compare** | "How does my audience perform on Google vs Meta vs LinkedIn?" |
| **List from CRM** | "Pull my Klaviyo VIP segment and upload to all ad platforms" |
| **Audience Cleanup** | "Remove audiences that haven't been used in 90 days" |

---

## Example Conversations

### 1. One List, Every Platform

> **You:** I have 15,000 customer emails. Upload them everywhere.
>
> **Agent:** I'll process your list for each platform's requirements and upload simultaneously.
>
> **Processing:**
> 1. Normalize emails (lowercase, trim whitespace)
> 2. SHA-256 hash each email (required by all platforms for privacy)
> 3. Format for each platform's API (field names, batch sizes, and structure differ)
>
> **Upload results:**
>
> | Platform | Uploaded | Matched | Match Rate | Audience Name |
> |---|---|---|---|---|
> | Google Ads | 15,000 | 10,200 | 68% | "Customers - March 2026" |
> | Meta Ads | 15,000 | 11,850 | 79% | "Customers - March 2026" |
> | LinkedIn | 15,000 | 8,700 | 58% | "Customers - March 2026" |
> | TikTok | 15,000 | 9,450 | 63% | "Customers - March 2026" |
> | X (Twitter) | 15,000 | 7,350 | 49% | "Customers - March 2026" |
> | Reddit | 15,000 | 6,600 | 44% | "Customers - March 2026" |
>
> **Match rates explained:** Meta has the highest match rate (79%) because most people use their real email for Facebook. LinkedIn is at 58% because many people use a work email, not the one in your CRM. Reddit is lowest (44%) because many users use anonymous emails.
>
> **Want me to create Lookalike audiences from this list on each platform?**

### 2. Tiered Audience Strategy

> **You:** I don't want to upload one big list. I want segments for different ad strategies.
>
> **Agent:** Smart. Let me build a tiered audience system:
>
> | Segment | Source | Size | Upload To | Purpose |
> |---|---|---|---|---|
> | VIPs (top 10% LTV) | CRM | 1,500 | Meta, Google | Lookalike seed (highest quality) |
> | All Customers | CRM | 15,000 | All platforms | Suppression (exclude from acquisition) |
> | Cart Abandoners | Shopify | 2,800 | Meta, Google, TikTok | Retargeting (recover lost sales) |
> | Pricing Page Visitors | GA4 | 4,200 | Google, LinkedIn | Retargeting (high-intent) |
> | Email Engaged | Klaviyo | 8,400 | Meta | Retargeting (warm audience) |
> | Churned Customers | CRM | 3,100 | Meta, Google | Win-back campaigns |
>
> **Audience hierarchy for campaigns:**
> - **Acquisition:** Target Lookalikes from VIPs, EXCLUDE all customers and cart abandoners
> - **Retargeting:** Target cart abandoners and pricing page visitors, EXCLUDE customers
> - **Win-Back:** Target churned customers with re-engagement offers
> - **Upsell:** Target all customers with new product launches
>
> Each layer has exclusions to prevent overlap — no one sees an acquisition ad AND a retargeting ad.

### 3. Match Rate Optimization

> **You:** My LinkedIn match rate is only 40%. How do I improve it?
>
> **Agent:** LinkedIn matches on professional email addresses, and most CRM lists contain personal emails. Here's how to improve:
>
> **Current match rate: 40% (6,000 of 15,000 matched)**
>
> **Improvement strategies:**
>
> 1. **Add company names (biggest impact):** LinkedIn can match by email + company name. If you have company data in your CRM, I can include it. Expected improvement: +15-20%.
>
> 2. **Add first/last names:** LinkedIn uses name + company as a secondary matching signal. Expected improvement: +5-10%.
>
> 3. **Upload work emails separately:** If you have work email addresses (from B2B lead gen), upload those as a separate field. LinkedIn matches work emails at 80%+ vs 40% for personal emails.
>
> **Combined approach:**
> | Data Fields | Estimated Match Rate |
> |---|---|
> | Email only (current) | 40% |
> | Email + Company Name | 55-60% |
> | Email + Company + First/Last | 60-65% |
> | Work Email + Company | 75-85% |
>
> **You:** We have company names for 80% of contacts. Add them.
>
> **Agent:** Re-uploading with company names... New match rate: 62% (9,300 matched). That's 3,300 more LinkedIn members you can now target — a 55% improvement.

### 4. Automated Monthly Refresh

> **You:** How do I keep my audiences fresh?
>
> **Agent:** Audiences decay — customers churn, new buyers aren't included, and contact info changes. Here's a refresh strategy:
>
> **Monthly refresh checklist:**
> 1. ✅ Pull latest customer list from CRM/Shopify/Klaviyo
> 2. ✅ Update VIP segment (recalculate top 10% by recent revenue)
> 3. ✅ Update suppression list (add new customers, remove churned)
> 4. ✅ Replace audiences on all platforms (upload new list, the platform handles diff)
> 5. ✅ Check Lookalike audiences still based on current seed
>
> **What I'll automate:**
> - Monthly pull from your connected CRM (HubSpot/Shopify/Klaviyo)
> - Re-upload to all 6 platforms
> - Log match rates and alert if any drop significantly (could indicate data quality issues)
>
> **Why monthly matters:** A 6-month-old customer list is targeting people who may have churned, changed emails, or no longer match your ICP. Fresh data = better targeting = lower CPA.
>
> Want me to set up the monthly refresh cycle?

### 5. Privacy-Compliant Audience Building

> **You:** Is uploading customer emails to ad platforms legal?
>
> **Agent:** It depends on your jurisdiction, but here's how the Synter MCP handles privacy:
>
> **What we do:**
> 1. **SHA-256 hashing:** All emails are hashed before upload. The ad platform never sees raw emails. They compare hashes to their user database — if there's a match, the user is added to your audience.
>
> 2. **No raw data stored:** The Synter MCP processes emails in memory and sends hashed values. We don't store your customer list.
>
> 3. **Platform compliance:** Google Customer Match, Meta Custom Audiences, LinkedIn Matched Audiences, and all other platforms require you to have consent to use customer data for advertising.
>
> **Your responsibilities:**
> - ✅ Ensure your privacy policy covers using customer data for advertising
> - ✅ Ensure you have consent (most Terms of Service cover this, but check yours)
> - ✅ Honor opt-out requests — remove anyone who objects
> - ✅ GDPR (EU): Legitimate interest OR explicit consent required
> - ✅ CCPA (California): Provide opt-out mechanism
>
> **Bottom line:** Customer Match / Custom Audiences are standard practice used by millions of advertisers. The hashing ensures privacy. But make sure your privacy policy and consent mechanisms cover ad targeting use.

---

## Audience Sync Tips

1. **Upload to ALL platforms simultaneously.** Your email list works on every platform. Don't leave money on the table by only uploading to one.
2. **Refresh audiences monthly.** Stale audiences = stale targeting. New customers get added, churned customers get removed.
3. **VIP customers make the best Lookalike seeds.** Top 10% by revenue outperforms "all customers" as a seed by 40-60% on CPA.
4. **Suppression saves 5-10% of budget.** Excluding existing customers from acquisition campaigns is the easiest budget optimization.
5. **Match rates vary by platform.** Meta matches 70-80%, Google 60-70%, LinkedIn 40-65% (work emails help). Don't compare platform performance without accounting for match rate differences.
6. **Add company names for LinkedIn.** LinkedIn match rates jump 15-20% when you include company name alongside email.
7. **Create separate audiences for different strategies.** VIPs → Lookalike seeds. All customers → Suppression. Cart abandoners → Retargeting. One-size-fits-all audience = one-size-fits-none.

---

## FAQ

### Is there an MCP for audience syncing across ad platforms?
Yes — this repo. It handles Customer Match (Google), Custom Audiences (Meta), Matched Audiences (LinkedIn), Custom Audiences (TikTok), Tailored Audiences (X), and more.

### How does email hashing work?
Emails are processed with SHA-256 hashing before upload. The ad platform compares hashes to their user database. Neither you nor the platform sees the other's raw data.

### Which platforms are supported?
Google Ads, Meta (Facebook/Instagram), LinkedIn, TikTok, X (Twitter), Reddit, and Amazon. Additional platforms are being added.

### Can I pull lists from my CRM automatically?
Yes. If your CRM (HubSpot, Salesforce, Attio, Pipedrive, Klaviyo) is connected, the agent can pull segments directly and upload to ad platforms.

### How often should I refresh audiences?
Monthly is the minimum. For fast-moving businesses (ecommerce, SaaS with monthly churn), bi-weekly is better.

---

## Related Repos

- [klaviyo-agent](https://github.com/Synter-Media-AI/klaviyo-agent) — Pull ecommerce segments
- [hubspot-agent](https://github.com/Synter-Media-AI/hubspot-agent) — Pull CRM contacts
- [shopify-agent](https://github.com/Synter-Media-AI/shopify-agent) — Pull customer data
- [meta-ads-agent](https://github.com/Synter-Media-AI/meta-ads-agent) — Meta Custom Audiences
- [google-ads-agent](https://github.com/Synter-Media-AI/google-ads-agent) — Google Customer Match
- [linkedin-ads-agent](https://github.com/Synter-Media-AI/linkedin-ads-agent) — LinkedIn Matched Audiences

---

## License

MIT — see [LICENSE](LICENSE) for details.

Built by [Synter](https://syntermedia.ai) · [Get API Key](https://syntermedia.ai/developer) · [Documentation](https://syntermedia.ai/docs)
