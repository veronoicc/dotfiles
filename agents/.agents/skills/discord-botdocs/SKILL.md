---
name: discord-botdocs
description: >
  Search and query official Discord Bot and Developer Platform documentation using the discord-botdocs MCP server.
  MUST ALWAYS BE USED whenever doing any work related to official Discord bots, application commands, interactions, webhooks, official Discord API endpoints, or developer platform docs.
---

# Discord BotDocs MCP Skill

Skill for searching and querying official Discord bot and developer platform documentation using the `discord-botdocs` MCP server.

## Mandatory Usage Invariant

> **MUST ALWAYS BE USED** whenever working on:
> - Official Discord bots or applications.
> - Application commands (slash commands, context menu commands), interactions, or components.
> - Bot gateway events, intents, sharding, or voice gateway.
> - Official REST API v10 endpoints, webhooks, or OAuth2 integrations.
> - Any query regarding official Discord developer platform documentation.

---

## MCP Server Tools (`discord-botdocs`)

### 1. `search_documentation_discord`
Search the official Discord documentation knowledge base for API references, concepts, data structures, and guides.
- **Parameters**: `query` (`str`)
- **Use when**: Looking up official Discord API endpoints, interaction structures, gateway events, bot permissions, or application command schemas.

### 2. `query_docs_filesystem_documentation_discord`
Query the virtualized, in-memory documentation filesystem containing Markdown pages and OpenAPI specs.
- **Parameters**: filesystem search query / path commands
- **Use when**: Browsing specific documentation sections, OpenAPI schema specs, or structured documentation files.

### 3. `submit_feedback`
Report broken, outdated, confusing, or incomplete documentation pages to the Discord docs team.
- **Parameters**: feedback report content
- **Use when**: Encountering incorrect or outdated information in official Discord API documentation.
