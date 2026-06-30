# Publishing Nishare Skill

This checklist is for distributing the Nishare API skill so more AI tool users can discover and install it.

## Priority 0: Publish Now

### GitHub

- Repository: `https://github.com/momofa/nishare`
- Purpose: source of truth for all marketplace and directory submissions.
- Required material:
  - `README.md`
  - `SKILL.md`
  - `AI_TOOLS.md`
  - `references/api.md`
  - packaged archives
  - license
- Suggested topics:
  - `nishare`
  - `ai-tools`
  - `ai-agents`
  - `codex-skill`
  - `markdown`
  - `html`
  - `publishing`
  - `share-links`

### Cursor Directory

- URL: `https://cursor.directory/`
- Fit: developers using Cursor can paste the agent prompt into project rules and publish generated HTML or Markdown directly to Nishare.
- Submit as: agent rule / AI tool integration.
- Required material:
  - short description
  - GitHub URL
  - `AI_TOOLS.md` prompt
  - example curl request

### MCP.Directory

- URL: `https://mcp.directory/submit`
- Fit: strong if Nishare is wrapped as an MCP server.
- Status: requires MCP wrapper before submission.
- Next action: create `nishare-mcp` server exposing `publish` and `update` tools.

### MCP Market

- URL: `https://mcpmarket.com/submit`
- Fit: same as MCP.Directory.
- Status: requires MCP wrapper before submission.

### Smithery

- URL: `https://smithery.ai/`
- Fit: strong MCP registry with install flow.
- Status: requires MCP server plus Smithery configuration.

## Priority 1: Productized Integrations

### OpenAI GPT / GPT Store

- URL: `https://help.openai.com/en/articles/8798878`
- Fit: create a GPT named `Nishare Publisher` that publishes HTML and Markdown through Nishare.
- Required material:
  - GPT instructions
  - OpenAPI schema for `/api/ai/publish` and `/api/ai/update`
  - privacy policy URL
  - API key instructions

### Claude Connector Directory

- URL: `https://claude.com/docs/connectors/building/submission`
- Fit: strong if Nishare becomes a Remote MCP server.
- Required material:
  - hosted Remote MCP server
  - auth flow
  - directory submission details

### VS Code Marketplace / Open VSX

- VS Code: `https://code.visualstudio.com/api/working-with-extensions/publishing-extension`
- Open VSX: `https://open-vsx.org/`
- Fit: publish selected file or editor content to Nishare.
- Status: requires a VS Code extension.

## Priority 2: Growth Channels

### Product Hunt

- URL: `https://www.producthunt.com/launch`
- Best angle: `Nishare for AI Agents`.
- Needs:
  - landing page
  - screenshots or demo video
  - clear use cases
  - founder comment

### Hacker News Show HN

- URL: `https://news.ycombinator.com/submit`
- Suggested title:

```text
Show HN: Nishare - publish HTML and Markdown pages from AI agents
```

### Dev.to / Hashnode

- Fit: tutorial content.
- Suggested article:

```text
How to let AI agents publish HTML and Markdown pages with a shareable URL
```

### Reddit

- Candidate communities:
  - `r/OpenAI`
  - `r/ClaudeAI`
  - `r/LocalLLaMA`
  - `r/cursor`
  - `r/webdev`
  - `r/SideProject`
- Note: read each community's self-promotion rules before posting.

### Awesome Lists

- Candidate categories:
  - AI agents
  - MCP servers
  - ChatGPT tools
  - developer productivity
  - Markdown publishing

## Recommended Sequence

1. Polish GitHub repository metadata, README, release, and topics.
2. Add an MCP server wrapper.
3. Submit to MCP.Directory, MCP Market, and Smithery.
4. Add OpenAPI schema and create a GPT Action.
5. Prepare screenshots or a short demo video.
6. Launch on Product Hunt and Show HN.
7. Post tutorials and community examples.

## One-Line Positioning

```text
Nishare lets AI agents publish HTML and Markdown content through an API, then instantly generate shareable web links.
```

Chinese version:

```text
Nishare 让 AI Agent 可以通过 API 发布 HTML 和 Markdown 内容，并自动生成可分享链接。
```
