---
name: atlassian-mcp
description: Fetch Confluence documents and Jira tickets using the Atlassian MCP server. Use when the user provides Confluence URLs (wiki/spaces), Jira issue URLs, or asks to view/read Atlassian content.
---

# Atlassian MCP

Retrieve and display Confluence pages and Jira issues using the Atlassian MCP server (`user-atlassian-mcp-server`).

## Quick Start

When given a Confluence or Jira URL:

1. **Extract identifiers from the URL**
   - Confluence: Extract `cloudId` (site URL) and `pageId` from the page URL path
   - Jira: Extract `cloudId` and issue key from the URL

2. **Check tool schema first**
   - Read the tool descriptor JSON from `C:\Users\rlennox\.cursor\projects\c-git\mcps\user-atlassian-mcp-server\tools\`
   - This ensures you know the exact parameters and format

3. **Call the appropriate MCP tool**
   - Confluence: `getConfluencePage`
   - Jira: `getJiraIssue`

4. **Display the result**
   - Content is returned as JSON (Confluence) or structured data
   - Present to the user in readable format

## URL Parsing

### Confluence URLs

Format: `https://certifid.atlassian.net/wiki/spaces/{spaceKey}/pages/{pageId}`

Extract:
- **cloudId**: `certifid.atlassian.net` (the site URL)
- **pageId**: Numeric ID from the URL path (e.g., `4374659098`)
- **contentFormat**: Default to `"markdown"` unless user specifies otherwise

Example:
```
URL: https://certifid.atlassian.net/wiki/spaces/~420116675/pages/4374659098/Proposed+Status+Refinement+02+09+26
→ cloudId: "certifid.atlassian.net"
→ pageId: "4374659098"
→ contentFormat: "markdown"
```

### Jira URLs

Format: `https://certifid.atlassian.net/browse/{issueKey}`

Extract:
- **cloudId**: `certifid.atlassian.net` (the site URL)
- **issueKey**: Issue identifier (e.g., `BUV-123`)

Example:
```
URL: https://certifid.atlassian.net/browse/BUV-346
→ cloudId: "certifid.atlassian.net"
→ issueKey: "BUV-346"
```

## Tool Reference

### Available Tools

| Tool | Purpose | Required Parameters |
|------|---------|---------------------|
| `getConfluencePage` | Fetch a Confluence page by ID | `cloudId`, `pageId` |
| `getJiraIssue` | Fetch a Jira issue | `cloudId`, `issueKey` |

### Before Calling: Always Check the Schema

Read the tool descriptor to verify parameter names and requirements:

```
C:\Users\rlennox\.cursor\projects\c-git\mcps\user-atlassian-mcp-server\tools\getConfluencePage.json
C:\Users\rlennox\.cursor\projects\c-git\mcps\user-atlassian-mcp-server\tools\getJiraIssue.json
```

**Why**: MCP tool signatures can change. Always read the schema to ensure correct parameter usage.

## MCP Server Details

- **Server name**: `user-atlassian-mcp-server`
- **Tool location**: `C:\Users\rlennox\.cursor\projects\c-git\mcps\user-atlassian-mcp-server\tools\*.json`
- **Authentication**: Uses browser session cookies (logged-in sessions are available)

## Implementation Pattern

```
1. User provides Confluence/Jira URL
   ↓
2. Read tool schema from descriptor file
   ↓
3. Extract identifiers from URL
   ↓
4. Call MCP tool with CallMcpTool
   ↓
5. Display result to user
```

## Examples

### Example 1: Fetch Confluence Page

```
User: "Can you view this confluence doc? https://certifid.atlassian.net/wiki/spaces/CP/pages/4417912833/RFC+Centralized+Request+Statuses"

Steps:
1. Read: C:\Users\rlennox\.cursor\projects\c-git\mcps\user-atlassian-mcp-server\tools\getConfluencePage.json
2. Extract: cloudId = "certifid.atlassian.net", pageId = "4417912833"
3. Call: CallMcpTool(server="user-atlassian-mcp-server", toolName="getConfluencePage", arguments={cloudId, pageId, contentFormat: "markdown"})
4. Display: Render the returned markdown content for the user
```

### Example 2: Fetch Jira Issue

```
User: "Can you pull up BUV-123 from Jira?"

Steps:
1. Read: C:\Users\rlennox\.cursor\projects\c-git\mcps\user-atlassian-mcp-server\tools\getJiraIssue.json
2. Extract: cloudId = "certifid.atlassian.net", issueKey = "BUV-123"
3. Call: CallMcpTool(server="user-atlassian-mcp-server", toolName="getJiraIssue", arguments={cloudId, issueKey})
4. Display: Render the issue details for the user
```

## Tips

- **Markdown format for Confluence**: Use `contentFormat: "markdown"` by default for readable output
- **Session already available**: No need to log in; your browser session is already authenticated
- **URL variations**: Confluence URLs may include page title after the ID; extract only the numeric pageId
- **Schema first**: Before calling any MCP tool, read its JSON descriptor to verify parameter names and requirements
