# Tendy MCP server: Israeli public tenders for AI assistants

[Tendy](https://tendy.co.il) collects Israeli public procurement tenders (מכרזים ציבוריים) from hundreds of government ministries, municipalities and state companies, reads the tender documents, and lays out what decides a bid: threshold conditions (תנאי סף), bid guarantee, deadline, site visit and required documents.

This repository documents Tendy's hosted MCP server, so Claude, ChatGPT, Cursor and other MCP clients can search and read Israeli tenders directly.

- **Endpoint:** `https://tendy.co.il/mcp`
- **Transport:** Streamable HTTP
- **Auth:** OAuth (sign in with your Tendy account). Full tender details need a Tendy subscription.
- **Language:** tender data is in Hebrew. Queries match best in Hebrew.
- **Registry:** [`io.github.ofir09/tendy`](https://registry.modelcontextprotocol.io/v0/servers?search=io.github.ofir09/tendy) in the official MCP Registry.

## Tools

| Tool | What it does |
| --- | --- |
| `search_tenders` | Search open tenders by free text and filters (category, region, publisher, tender number). |
| `get_tender` | One tender: what is being bought, deadlines, threshold conditions, requirements, budget, contacts and documents. |
| `search_tender_documents` | Search inside a tender's PDFs and return the relevant passages with their source document. |
| `list_categories` | Tendy's tender categories: 13 parent categories and their subcategories. |
| `list_collections` / `browse_collection` | Public hub pages: tenders by category, publishing body or region, including government and municipal tenders. |
| `list_my_feed` | Tenders that pass your Tendy profile filters (categories, regions, budget). |
| `get_my_profile` / `update_my_profile` | Read or change those filters. |

## Connect

**Claude** (claude.ai or Claude Desktop): Settings, Connectors, Add custom connector, paste `https://tendy.co.il/mcp`, then sign in.

**Cursor / VS Code / other clients** that support remote servers:

```json
{
  "mcpServers": {
    "tendy": {
      "url": "https://tendy.co.il/mcp"
    }
  }
}
```

The client opens the Tendy sign-in page on first use.

## Example questions

- "אילו מכרזי ניקיון פתוחים יש בצפון?"
- "מה תנאי הסף במכרז 12/2026 של עיריית חיפה?"
- "Find open infrastructure tenders closing in the next two weeks and summarize their bid guarantees."
- "באיזה מסמך במכרז הזה כתוב מה צריך להגיש?"

## בעברית

Tendy מסדרת מכרזים ציבוריים בישראל: אוספת אותם ממאות גופים, קוראת את מסמכי המכרז ומרכזת את מה שמכריע, תנאי סף, ערבות, מועד הגשה ומה צריך להגיש. שרת ה-MCP מאפשר לחבר את Tendy ל-Claude, ל-ChatGPT ולכלים נוספים, ולשאול על מכרזים ישירות מהשיחה.

אתר: [tendy.co.il](https://tendy.co.il) · מכרזים לפי תחום: [tendy.co.il/tenders](https://tendy.co.il/tenders) · מכרזים ממשלתיים: [tendy.co.il/tenders/government](https://tendy.co.il/tenders/government) · מכרזי רשויות מקומיות: [tendy.co.il/tenders/municipal](https://tendy.co.il/tenders/municipal)

## Support

[tendy.co.il/support](https://tendy.co.il/support)
