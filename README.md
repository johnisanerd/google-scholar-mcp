# Google Scholar MCP Server

> Search Google Scholar for academic papers, citations, and author profiles. Use with Claude, Cursor, or any MCP client.

This is a remote MCP server that lets Claude, Cursor, ChatGPT, or any MCP client query Google Scholar directly as a tool call.

## Install in Claude Desktop

Add this to your `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "google-scholar": {
      "url": "https://apify.com/johnvc/google-scholar-api/api/mcp"
    }
  }
}
```

Restart Claude Desktop. The new tool will be available in your conversations.

## Install in Cursor

Add this to your `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "google-scholar": {
      "url": "https://apify.com/johnvc/google-scholar-api/api/mcp"
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

[johnvc on Apify](https://apify.com/johnvc?fpr=9n7kx3) | [Sign up for a free account here](https://apify.com/?fpr=9n7kx3).

## License

MIT
