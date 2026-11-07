# Security policy

## Scope

This repository holds plugin manifests only. The plugin runs no code on your machine; it declares a remote, read-only MCP server at `https://mcp.wirelesschoices.com.au/mcp` operated by Wireless Choices Pty Ltd. Reports about the server, the plugin files, the plan data or the outage data are all welcome here.

## Reporting a vulnerability

Email **contact@wirelesschoices.com** with the subject line `Security: plugin`. Include what you found, how to reproduce it and, if relevant, the tool call and response. Do not open a public issue for a security report.

We acknowledge reports within two business days, investigate with reasonable care, and tell you when the issue is resolved. Please give us a reasonable time to fix a problem before disclosing it publicly.

## Out of scope

- Rate limiting thresholds on the public server
- Plan data that has changed on a provider's site since the date shown on the result, or an outage register entry a carrier has since corrected (report these as accuracy concerns to the same address and we will check them against the provider's published terms or register)
