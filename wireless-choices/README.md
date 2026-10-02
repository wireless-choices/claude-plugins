# Wireless Choices — plan finder for Claude

Search and compare Australian mobile, prepaid, mobile broadband and nbn home internet plans listed on Wireless Choices, without leaving Claude. Every result carries the date it was last updated on Wireless Choices and a link to its plan page on wirelesschoices.com.au.

## What it does

- `search_plans` — filter by price, included data, network, speed tier, contract and features such as 5G, eSIM, data rollover and international calls. Up to five results per search, with the total number of matching plans stated.
- `get_plan` — one plan in detail, including inclusions and the promotion terms recorded for it on Wireless Choices.
- `compare_plans` — two to four plans side by side.
- `list_providers` — the providers listed on Wireless Choices and the network each sells access to.

Results are ordered by lowest ongoing price among the plans that match your filters, with ties ordered by included data. Most-data and lowest-price-per-GB orderings are available on request. The ordering method is stated with every result, and no plan is ranked, scored or recommended.

## Example prompts

- "Find me a prepaid plan with at least 50GB for under $35."
- "Which nbn 100 plans have no lock-in contract?"
- "Compare the SpinTel 25GB Mobile Plan with the swoop 30GB Mobile Plan."

## Install

No account, API key or login is needed. In Claude Code:

```
/plugin marketplace add wireless-choices/claude-plugins
/plugin install wireless-choices@wirelesschoices
```

In Claude, add the server URL `https://mcp.wirelesschoices.com.au/mcp` as a custom connector with no authentication, or add the plugin from the directory once listed.

## What is compared

Plans from providers listed on Wireless Choices only. Not every provider or plan in the Australian market is listed. Plans flagged on the site as sponsored or partner-exclusive are not returned by this tool. Network names describe the network a provider sells access to, not coverage at your address; availability at a specific address is checked on the plan page, not by this tool.

## Accuracy and freshness

Plan data is not live. The server answers from a copy of the Wireless Choices catalogue that is refreshed every 15 minutes, and each plan carries the date Wireless Choices last recorded a change to it. Prices, inclusions, offers and eligibility conditions can change between our checks, and offers can end or be withdrawn at any time. Where an offer is shown, the offer price, its length, the standard price that follows, any eligibility condition and any end date are stated as recorded. Always confirm the current price, terms and your eligibility on the provider's website before you sign up.

## Not advice

The information returned by this tool is general information only. It does not take account of your needs, usage or circumstances and is not financial, legal or telecommunications advice. Consider whether a plan suits you before acting on it.

## Commission disclosure

Wireless Choices may earn a commission if you connect to a plan through links on wirelesschoices.com.au. Commission does not affect which plans are returned or how they are ordered in this tool. Prices are as published by each provider on the date shown.

## Privacy

The server receives only the search filters Claude sends on your behalf (for example plan type, price limit, data amount). It does not receive your conversation, your name, your address or your contact details, and it stores none of them. Aggregate usage counts (tool used, plan type, result count, response time) are recorded with no personal information. Links from the tool go to wirelesschoices.com.au, where the Wireless Choices privacy policy applies: https://wirelesschoices.com.au/privacy-policy#ai-assistants

## What this plugin runs, sends and fetches

This plugin contains no code of its own. It declares one remote MCP server, `https://mcp.wirelesschoices.com.au/mcp`, which Claude calls over HTTPS when you ask about Australian telco plans. Nothing is installed or executed on your machine. The only data sent to the server is the tool call Claude makes on your behalf: the tool name and its arguments (plan type, price limit, data amount, network, provider slug, plan slug, feature filters). The server is read-only, rate-limited and returns plan data and links to plan pages on wirelesschoices.com.au. It never links to providers or affiliate networks directly, does not serve advertising or sponsored content, and does not request credentials or environment variables.

## Support and security

Product questions, accuracy concerns and security reports: contact@wirelesschoices.com. Security reports are acknowledged within two business days and investigated by the operator of the server. If you believe a plan is shown incorrectly, tell us and we will check it against the provider's published terms.

## Legal

The files in this folder are licensed under the MIT Licence in `LICENSE`. The licence covers these files only; the server, the data it returns and the Wireless Choices name, logo and site content are not licensed and are governed by the Wireless Choices Terms of Service. Terms of use, copyright and trade mark notices are in `NOTICE.md`.
