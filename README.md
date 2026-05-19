# Google Scholar MCP Server

> Search Google Scholar for academic papers, citations, and author profiles.

This is a remote MCP server that lets Claude, Cursor, ChatGPT, or any MCP client query Google Scholar directly as a tool call.  Review the documentation [here](https://apify.com/johnvc/google-scholar-api?fpr=9n7kx3).

## Login

You'll need an Apify API token to login. A free Apify account works. Get yours at [console.apify.com/account#/integrations](https://console.apify.com/account#/integrations?fpr=9n7kx3).

## Install in Claude Desktop

Claude Desktop currently requires a stdio bridge for remote MCP servers. Add this to your `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "google-scholar": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://mcp.apify.com/?tools=johnvc/google-scholar-api",
        "--header",
        "Authorization: Bearer <YOUR_APIFY_TOKEN>"
      ]
    }
  }
}
```

Replace `<YOUR_APIFY_TOKEN>` with your token. Restart Claude Desktop.

## Install in Cursor

Cursor supports remote MCP servers natively. Two ways to connect:

### Option A: OAuth (recommended, no token needed)

Add this to your `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "google-scholar": {
      "url": "https://mcp.apify.com/?tools=johnvc/google-scholar-api"
    }
  }
}
```

The first connection opens a browser to sign in to Apify.

### Option B: Bearer token

```json
{
  "mcpServers": {
    "google-scholar": {
      "url": "https://mcp.apify.com/?tools=johnvc/google-scholar-api",
      "headers": {
        "Authorization": "Bearer <YOUR_APIFY_TOKEN>"
      }
    }
  }
}
```

## What it does

This MCP server lets Claude search Google Scholar for academic papers, retrieve citation counts, fetch author profiles, and pull abstracts. Useful for literature reviews, citation tracking, prior-art research, and "what's been written about X?" queries. Returns structured JSON with paper title, authors, citation count, abstract, PDF link, and publication year.

Example queries to try in Claude:

- "Find the 10 most-cited papers on transformer architecture published since 2023"
- "Get the author profile and h-index for Yoshua Bengio"
- "Search Google Scholar for recent papers on RAG retrieval performance"

## Built by

[johnvc on Apify](https://apify.com/johnvc?fpr=9n7kx3) | [Sign up for a free Apify account](https://apify.com/?fpr=9n7kx3).

## License

MIT
