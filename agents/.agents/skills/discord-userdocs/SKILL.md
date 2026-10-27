---
name: discord-userdocs
description: >
  Search and fetch unofficial Discord User API, Userbot, and Selfbot documentation using the discord-userdocs MCP server.
  MUST ALWAYS BE USED whenever doing any work related to Discord userbots, selfbots, user account automation, raw user tokens, reverse-engineered user API endpoints, or user-side API documentation.
---

# Discord UserDocs MCP Skill

Skill for searching and retrieving unofficial Discord User API and userbot documentation using the `discord-userdocs` MCP server.

## Mandatory Usage Invariant

> **MUST ALWAYS BE USED** whenever working on:
> - Userbots, selfbots, or user account automation.
> - Raw user token authentication, user-side REST endpoints (`/users/@me`, `/relationships`, `/settings-proto`, `/experiments`).
> - User Gateway connections, Gateway Capabilities bitfield, or User Intents.
> - Reverse-engineered user-side Discord features or user documentation.

---

## MCP Server Tools (`discord-userdocs`)

### 1. `search_docs`
Semantically search the unofficial Discord User API documentation knowledge base.
- **Parameters**: `query` (`str`)
- **Use when**: Searching for userbot topics, selfbot guidance, user token behavior, Gateway capabilities, or reverse-engineered user endpoint specifications.

### 2. `fetch_page`
Fetch the complete Markdown content of a specific documentation page.
- **Parameters**: `page_path` or topic path from search results
- **Use when**: Retrieving full details, code samples, or full endpoint schemas after executing `search_docs`.
