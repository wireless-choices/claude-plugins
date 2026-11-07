# Wireless Choices — plans and outage reports for Claude

Search and compare Australian mobile, prepaid, mobile broadband and nbn home internet plans listed on Wireless Choices, and check outage reports and resolved outage history for Australian providers, without leaving Claude. Every plan carries the date it was last updated on Wireless Choices and a link to its plan page on wirelesschoices.com.au.

## What it does

Plans:

- `search_plans` — filter by price, included data, network, speed tier, contract and features such as 5G, eSIM, data rollover and international calls. Up to 10 results per search, with the total number of matching plans stated; the first 50 matches can be paged.
- `get_plan` — one plan in detail, including inclusions and the promotion terms recorded for it on Wireless Choices.
- `compare_plans` — two to four plans side by side.
- `list_providers` — the providers listed on Wireless Choices and the network each sells access to.

Outages:

- `get_outage_status` — for one provider, one Australian postcode, or a provider in a postcode: the number of community outage reports made on Wireless Choices in the last 24 hours and the last 7 days by issue type, how many reports the counts are based on, and the most recent resolved outages published on the carrier outage registers required by the ACMA.
- `get_outage_history` — resolved outages from the Telstra, Optus, TPG Telecom (Vodafone) and nbn outage registers, by provider, postcode or state. Up to 10 entries per request; the first 30 can be paged.

Plan results are ordered by lowest ongoing price among the plans that match your filters, with ties ordered by included data. Most-data and lowest-price-per-GB orderings are available on request. The ordering method is stated with every result, and no plan is ranked, scored or recommended. Outage results are never used to rank or compare providers or networks.

## Example prompts

- "Find me a prepaid plan with at least 50GB for under $35."
- "Which nbn 100 plans have no lock-in contract?"
- "Compare the SpinTel 25GB Mobile Plan with the swoop 30GB Mobile Plan."
- "Have people reported Optus problems in postcode 4280 this week?"
- "Show recent resolved outages on the Vodafone network in NSW."

## Install

No account, API key or login is needed. In Claude Code:

```
/plugin marketplace add wireless-choices/claude-plugins
/plugin install wireless-choices@wirelesschoices
```

In Claude, add the server URL `https://mcp.wirelesschoices.com.au/mcp` as a custom connector with no authentication, or add the plugin from the directory once listed.

## What is compared

Plans from providers listed on Wireless Choices only. Not every provider or plan in the Australian market is listed. Plans flagged on the site as sponsored or partner-exclusive are not returned by this tool. Network names describe the network a provider sells access to, not coverage at your address; availability at a specific address is checked on the plan page, not by this tool.

## About the outage data

- **Community reports** are made on Wireless Choices by members of the public and are not confirmed by the provider. Volumes are small, so a low or zero count does not mean there is no outage. In a postcode, counts of 1 or 2 are shown as "1-2" to protect the people who reported.
- **Register entries** are resolved outages that each carrier has published under the ACMA outage-register rules. They are records of past outages, not current network status, and only cover outages above the ACMA size and duration thresholds. Each entry is attributed to the carrier that published it, with a link to that carrier's register.
- For a provider that uses another carrier's network, register entries come from that host network and are labelled as on that network.
- Larger networks publish more register entries, so counts do not show which provider or network has fewer outages.
- For current network status, check the provider's own service status page.

## Accuracy and freshness

Plan data is not live. The server answers from a copy of the Wireless Choices catalogue that is refreshed every 15 minutes, and each plan carries the date Wireless Choices last recorded a change to it. Prices, inclusions, offers and eligibility conditions can change between our checks, and offers can end or be withdrawn at any time. Where an offer is shown, the offer price, its length, the standard price that follows, any eligibility condition and any end date are stated as recorded. Always confirm the current price, terms and your eligibility on the provider's website before you sign up.

Outage data is refreshed from the same server every 15 minutes, and every outage result states the time it is as of. Register entries are added when Wireless Choices next collects them from each carrier's register.

## Not advice

The information returned by this tool is general information only. It does not take account of your needs, usage or circumstances and is not financial, legal or telecommunications advice. Consider whether a plan suits you before acting on it.

## Commission disclosure

Wireless Choices may earn a commission if you connect to a plan through links on wirelesschoices.com.au. Commission does not affect which plans are returned or how they are ordered in this tool. Prices are as published by each provider on the date shown.

## Privacy

The server receives only the arguments Claude sends on your behalf: plan search filters (for example plan type, price limit, data amount), and for outage lookups a provider, a four-digit postcode or a state. It does not receive your conversation, your name, your street address or your contact details, and it stores none of them. Postcodes are used only to answer the lookup and are not recorded. Aggregate usage counts (tool used, plan type or kind of outage lookup, result count, response time) are recorded with no personal information. Outage report counts are aggregated: no individual report, and nothing that identifies a reporter, is returned. Links from the tool go to wirelesschoices.com.au, where the Wireless Choices privacy policy applies: https://wirelesschoices.com.au/privacy-policy#ai-assistants

## What this plugin runs, sends and fetches

This plugin contains no code of its own. It declares one remote MCP server, `https://mcp.wirelesschoices.com.au/mcp`, which Claude calls over HTTPS when you ask about Australian telco plans or outages. Nothing is installed or executed on your machine. The only data sent to the server is the tool call Claude makes on your behalf: the tool name and its arguments (plan type, price limit, data amount, network, provider slug, plan slug, feature filters, postcode, state, outage type). The server is read-only and rate-limited. It returns plan data with links to plan pages on wirelesschoices.com.au, and outage data with links to Wireless Choices outage pages and to each carrier's published outage register. It never links to provider sales pages or affiliate networks, does not serve advertising or sponsored content, and does not request credentials or environment variables.

## Support and security

Product questions, accuracy concerns and security reports: contact@wirelesschoices.com. Security reports are acknowledged within two business days and investigated by the operator of the server. If you believe a plan or outage entry is shown incorrectly, tell us and we will check it against the provider's published terms or register.

## Legal

The files in this folder are licensed under the MIT Licence in `LICENSE`. The licence covers these files only; the server, the data it returns and the Wireless Choices name, logo and site content are not licensed and are governed by the Wireless Choices Terms of Service. Terms of use, copyright and trade mark notices are in `NOTICE.md`.
