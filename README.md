<img src="logo-400.png" alt="SamDesk Support logo" width="96" height="96">

# SamDesk Support MCP server

**Read your SamDesk support inbox, find customer agreements and draft replies. Read-only.**

Remote MCP server: `https://samdesk.nl/support/mcp` (Streamable HTTP) · Website: [samdesk.nl/support/plugin](https://samdesk.nl/support/plugin/)

## What it does

SamDesk Support lets an AI assistant read selected conversations from your SamDesk support inbox, find what was agreed with a customer in earlier messages, and draft a reply in the chat. You send the reply yourself from SamDesk.

Read-only. It does not send messages, change conversations or save drafts.

## Connect

- **Server URL:** `https://samdesk.nl/support/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with PKCE (S256), dynamic client registration and client ID metadata documents, so MCP clients connect without manual setup. Sign in with your SamDesk account.

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the server URL.

**Claude Code:**

```bash
claude mcp add --transport http samdesk-support https://samdesk.nl/support/mcp
```

**Cursor, VS Code, Cline, Windsurf and other clients** (`mcp.json` / `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "samdesk-support": {
      "type": "http",
      "url": "https://samdesk.nl/support/mcp"
    }
  }
}
```

Cline uses `"type": "streamableHttp"`; see [llms-install.md](llms-install.md).

## Tools

| Tool | What it does |
|---|---|
| `support_account / list_inboxes` | Account and inboxes. |
| `search_conversations / get_conversation` | Find and read conversations. |
| `customer_conversations` | All conversations with one customer. |

## Example prompts

- What did we agree with customer De Vries about the delivery date?
- Show unanswered conversations from today.
- Draft a reply to the last email from Bakkerij Smit.

## Links

- Website: https://samdesk.nl/support/plugin/
- Documentation: https://samdesk.nl/support/plugin/
- Privacy policy: https://samdesk.nl/support/plugin/privacy/
- Terms: https://samdesk.nl/nl/terms-of-service/
- Support: mailto:support@samdesk.nl

## Keywords

helpdesk, shared inbox, customer support AI, support ticket search, reply drafting.

Nederlands: klantenservice software, gedeelde inbox, helpdesk, klantgesprekken zoeken, antwoord opstellen.

## More MCP servers by Samautomation

- [Scamchecker.nl](https://scamchecker.nl/): Check a suspicious email, SMS, WhatsApp message or link for scam signals (Netherlands, Belgium). ([listing](https://github.com/smrht/scamchecker-mcp))
- [Klussenbeheer](https://samdesk.nl/klussenbeheer/): Job management for Dutch service companies: jobs, customers, planning, quotes and invoices. ([listing](https://github.com/smrht/klussenbeheer-mcp))
- [Muziek maken met AI](https://muziekmakenmetai.nl/): Make an original song from a prompt or your own lyrics. Two versions per song, MP3 download. ([listing](https://github.com/smrht/muziekmakenmetai-mcp))
- [Beheer je WP](https://beheerjewp.nl/): Manage a WordPress site from your AI assistant: read, search, propose edits, Search Console data. ([listing](https://github.com/smrht/beheerjewp-mcp))
- [UlazAI Media](https://ulazai.com/): Create private AI images with your UlazAI account: pick a model, confirm, generate, download. ([listing](https://github.com/smrht/ulazai-mcp))
- [Backlinkswinkel](https://backlinkswinkel.nl/): Search Dutch websites for backlinks, check metrics and prices, order after confirmation, track. ([listing](https://github.com/smrht/backlinkswinkel-mcp))
- [Backlinksbeheer](https://backlinksbeheer.nl/): Read your stored backlinks, link checks and lost-link alerts per domain. Read-only. ([listing](https://github.com/smrht/backlinksbeheer-mcp))
- [Samautomation Video](https://samautomation.work/): Render an MP4 from your own images, clips, voice-over and timed captions. JSON to video. ([listing](https://github.com/smrht/samautomation-video-mcp))
- [PDF Samenvoegen](https://pdfsamenvoegen.nl/): Merge your own PDFs in a confirmed order and get one downloadable PDF. ([listing](https://github.com/smrht/pdfsamenvoegen-mcp))
- [Diamond Painting Converter](https://diamondpaintingconverter.com/): Find your purchased diamond painting patterns and download the PDF with DMC colour legend. ([listing](https://github.com/smrht/diamondpaintingconverter-mcp))
- [Nummerschilderen.com shop advisor](https://nummerschilderen.com/): Search paint-by-number kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/nummerschilderen-mcp))
- [DiamondPaintingWinkel.nl shop advisor](https://diamondpaintingwinkel.nl/): Search diamond painting kits, get size and price advice for your own photo, shop info. No login. ([listing](https://github.com/smrht/diamondpaintingwinkel-mcp))
- [AI Rechtshulp](https://ai-rechtshulp.nl/): Search Dutch and EU case law with ECLI sources and verify quotes against the judgment. ([listing](https://github.com/smrht/ai-rechtshulp-mcp))

## Publisher

Samautomation, Wognum, the Netherlands · https://samautomation.work

This repository holds the public listing (README, `server.json`, install notes). The server itself is hosted by the publisher; there is nothing to install or build.
