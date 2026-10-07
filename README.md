# Cryptowisser News

Crypto news from [Cryptowisser](https://www.cryptowisser.com), an independent crypto newsroom, inside your AI assistant. Ask about crypto in plain language and get answers built on Cryptowisser's latest reporting, with news cards and links to the full stories.

It's a free, public, read-only remote MCP server. No account, API key or sign-in is needed.

```
https://www.cryptowisser.com/mcp/server
```

This repository also contains the Cryptowisser News plugin for Claude, which bundles the server with a skill that teaches Claude how to use it.

## Add it to your assistant

**Claude** (claude.ai, Desktop, mobile): find **Cryptowisser News** in the connectors directory under **Customize → Connectors**, or add it as a custom connector with the address above and choose **No sign in**.

**ChatGPT**: add a custom MCP server under **Settings → Plugins** with the address above and no authentication, then type `@` in a chat and pick it.

**Claude Code**:

```bash
claude mcp add --transport http cryptowisser-news https://www.cryptowisser.com/mcp/server
```

**Cursor**, in `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "cryptowisser-news": {
      "url": "https://www.cryptowisser.com/mcp/server"
    }
  }
}
```

**VS Code**, in `.vscode/mcp.json`:

```json
{
  "servers": {
    "cryptowisser-news": {
      "type": "http",
      "url": "https://www.cryptowisser.com/mcp/server"
    }
  }
}
```

**OpenClaw**, from ClawHub:

```bash
openclaw plugins install clawhub:cryptowisser-news
```

This installs the server together with the Cryptowisser News skill. Remote MCP servers in plugins need a recent OpenClaw release.

**Any other MCP client**: connect to the address above using the streamable HTTP transport, with no authentication.

## Tools

| Tool | What it does |
| --- | --- |
| `latest-news` | The latest crypto news, with the stories Cryptowisser's editors feature first, optionally for a date range or category |
| `news-about` | News about a coin, token, exchange, company, person, regulator, country or story. Tickers and aliases such as "ETH" or "CZ" are recognised |
| `trending-stories` | The biggest ongoing stories of the past week, each with its latest articles |
| `search-news` | Keyword search across Cryptowisser's archive, filterable by date |
| `get-article` | The full text of a Cryptowisser article, by URL or slug |

Every article comes with its headline, summary, author, publication date, age, topics, tags and a link to the original. In clients that support MCP Apps, list results render as news cards with images.

## Example questions

- "What's the latest crypto news?"
- "What's happening with Binance?" or "Any news about Michael Saylor?"
- "What are the biggest crypto stories this week?"
- "Find articles about stablecoin regulation from the last two weeks."
- "Summarize this article: https://www.cryptowisser.com/news/..."

## Data

The server only receives the requests your assistant sends to it, such as a search term, the name of a coin, company or person, or a date range. Your conversations are not sent to Cryptowisser. Cryptowisser keeps request logs for up to 30 days to operate and improve the service, as described in its [Privacy Policy](https://www.cryptowisser.com/privacy-policy/). The plugin in this repository runs no code on your machine and stores nothing itself.

Cryptowisser's news coverage is never paid for, and press releases and sponsored content are not included.

## Support

- Setup guide: https://www.cryptowisser.com/mcp/
- Questions or problems: support@cryptowisser.com

The plugin files in this repository are MIT licensed. The Cryptowisser News server and its content are operated by Dgtl Assets Group AB.
