# SA Business Calendar MCP

Hosted [Model Context Protocol](https://modelcontextprotocol.io) server that gives AI agents exact South African business-day answers: public holidays (including Sunday-to-Monday observed days and once-off declared holidays), business-day maths, and SARS EMP201/VAT201 due dates.

**Get it on Apify Store → [apify.com/ali_mora/sa-calendar-apify](https://apify.com/ali_mora/sa-calendar-apify)**

[![SA Business Calendar MCP server](https://mcprush.com/badge/sa-business-calendar-mcp/card.svg)](https://mcprush.com/to/sa-business-calendar-mcp?ref=badge)

## Tools

| Tool | What it does | Price |
|---|---|---|
| `is_business_day` | Is a date a weekend or SA public holiday? Returns the reason. | Free |
| `days_until_next_holiday` | Next SA public holiday after a date, and the days until it. | Free |
| `add_business_days` | Add or subtract SA business days, skipping weekends and holidays. | $0.01/call |
| `business_days_between` | Count SA business days between two dates. | $0.01/call |
| `holidays_in_range` | List SA public holidays between two dates. | $0.01/call |
| `next_sars_deadlines` | Next EMP201 and VAT201 due dates, adjusted for weekends and holidays. | $0.01/call |

Billed per call through Apify. Failed calls aren't charged.

## Connect

Endpoint (Streamable HTTP), authenticated with your [Apify API token](https://console.apify.com/account/integrations):

```
https://ali-mora--sa-calendar-apify.apify.actor/mcp
```

**Any MCP client:**

```json
{
  "mcpServers": {
    "sa-business-calendar": {
      "url": "https://ali-mora--sa-calendar-apify.apify.actor/mcp",
      "headers": { "Authorization": "Bearer <APIFY_TOKEN>" }
    }
  }
}
```

**Claude Code:**

```bash
claude mcp add --transport http sa-business-calendar https://ali-mora--sa-calendar-apify.apify.actor/mcp --header "Authorization: Bearer <APIFY_TOKEN>"
```

## Example prompts

- "Invoice dated 14 December 2026 on 5-business-day terms. When is it due?"
- "When are my next EMP201 and VAT201 payments due?"
- "List every SA public holiday between now and the end of March."

## Notes

- Dates are `YYYY-MM-DD`. National public holidays only; no provincial or bank-specific days.
- SARS rules are simplified (monthly VAT vendors). Verify against [sars.gov.za](https://www.sars.gov.za) before relying on them for filing.
- This repo holds the listing and registry metadata. The server source is private.

Issues and requests: open an issue here or on the Apify Store page.
