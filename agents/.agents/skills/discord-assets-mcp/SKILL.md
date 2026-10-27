---
name: discord-assets-mcp
description: >
  Search, inspect, and reverse-engineer compiled Discord web client JavaScript and CSS assets using the discord-js MCP server.
  MUST ALWAYS BE USED whenever doing any work related to discovering Discord client internals, compiled JS/CSS assets, Webpack modules, Flux stores, dispatchers, experiments, or developing Discord client mods (Vencord, BetterDiscord, Vesktop, Equicord, Shelter).
---

# Discord Assets MCP Skill

Skill for searching, indexing, inspecting, and reverse-engineering compiled Discord web client assets using the `discord-js` MCP server.

## Mandatory Usage Invariant

> **MUST ALWAYS BE USED** whenever working on:
> - Discovering or reverse-engineering Discord web/desktop client internals.
> - Searching compiled JavaScript and CSS bundles for Webpack modules, exported functions, or Flux Stores (`*Store`).
> - Finding Dispatcher ActionTypes (`MESSAGE_CREATE`, `VOICE_STATE_UPDATE`) or store handlers.
> - Developing, updating, or debugging Discord client mods (Vencord, BetterDiscord, Vesktop, Equicord, Shelter, Replugged).
> - Finding internal client routes, feature flags, experiments, or CSS class names (`className`).

---

## MCP Server Tools (`discord-js`)

### 1. `discord_targets`
List supported Discord web targets and check cache freshness (`last_cached_at`).
- **Targets**: `canary_app`, `canary_dev_portal`, `ads_portal`
- **Use when**: Verifying available targets or checking if bundle caches are up to date.

### 2. `refresh_discord_js`
Fetch and index the latest compiled JavaScript and CSS bundles from Discord servers.
- **Parameters**: `targets` (`list[str]`), `force` (`bool`)
- **Use when**: Initializing cache or pulling updated client builds.

### 3. `discord_build_overview`
Get a high-level summary of cached builds, including bundle labels, client routes, REST endpoints, and notable identifiers.
- **Parameters**: `targets` (`list[str]`)
- **Use when**: Getting an initial overview of bundle contents and indexed surfaces.

### 4. `discord_js_index`
View specific indexed sections across compiled bundles.
- **Sections**: `routes`, `endpoints`, `exports`, `notable_identifiers`, `tokens`
- **Parameters**: `target` (`str`), `section` (`str`), `limit` (`int`)
- **Use when**: Browsing Webpack export names, REST endpoint paths, or store/action identifiers.

### 5. `search_discord_js`
Search cached JavaScript and CSS bundles for code matches, returning compact snippets.
- **Parameters**: `query` (`str`), `target` (`str`), `facet` (`str`)
- **Use when**: Fast searching for specific function names, store names, or string literals.

### 6. `search_discord_js_context`
Search cached bundles and return larger code context snippets around matches.
- **Parameters**: `query` (`str`), `target` (`str`), `context_lines` (`int`)
- **Use when**: Inspecting logic flow or surrounding code around a search hit.

### 7. `inspect_discord_js_match`
Expand a code window around a specific search match offset.
- **Parameters**: `target`, `filename`, `start`, `end`, `context_chars`
- **Use when**: Reconstructing complete Webpack module definitions (`{ ... }`) for client mod patches.

### 8. `view_discord_js_file`
Read a slice of a cached JavaScript or CSS asset file.
- **Parameters**: `target`, `filename`, `start`, `max_chars`
- **Use when**: Reading raw bundle content around known file offsets.

### 9. `list_discord_js_files`
List cached JavaScript and CSS asset files.
- **Parameters**: `target`, `include_index` (`bool`)
- **Use when**: Inspecting bundle file lists and sizes.
