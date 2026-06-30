# Nishare API Skill

Publish HTML, Markdown, images, and generated documents from AI tools to Nishare, then return a shareable URL.

Nishare is useful when an AI agent creates a web page, report, demo, document, or image and the user wants a link they can immediately share with teammates, clients, or the public.

## What This Repository Contains

- `SKILL.md`: Codex skill instructions for publishing and updating Nishare shares.
- `AI_TOOLS.md`: Copyable prompt for ChatGPT, Claude, Cursor, Cherry Studio, Coze, Dify, and other AI tools.
- `references/api.md`: Full API reference with request fields, response shapes, limits, and examples.
- `agents/openai.yaml`: Agent metadata for OpenAI-style tool directories.
- `index.html`: Lightweight documentation page.
- `nishare-api.tar.gz`: Packaged Codex skill archive.
- `nishare-ai-tools.tar.gz`: Packaged generic AI tools prompt archive.

## Quick Start

### Anonymous Publish

```bash
curl -s https://nishare.com/api/ai/publish \
  -H 'Content-Type: application/json' \
  -d '{"title":"AI demo","type":"html","html":"<!doctype html><html><body><h1>Hello Nishare</h1></body></html>"}'
```

The response includes a `shareUrl`:

```json
{
  "id": "abc123",
  "shareUrl": "https://nishare.com/p/abc123"
}
```

### Publish With API Key

```bash
curl -s https://nishare.com/api/ai/publish \
  -H 'Content-Type: application/json' \
  -H 'X-Nishare-Key: nsk_xxx' \
  -d '{"title":"AI demo","type":"html","html":"<!doctype html><html><body><h1>Hello Nishare</h1></body></html>"}'
```

### Publish Markdown

```bash
curl -s https://nishare.com/api/ai/publish \
  -H 'Content-Type: application/json' \
  -d '{"title":"Release notes","type":"markdown","markdown":"# Release notes\n\nPublished from an AI agent."}'
```

### Update An Existing Project

```bash
curl -s https://nishare.com/api/ai/update \
  -H 'Content-Type: application/json' \
  -H 'X-Nishare-Key: nsk_xxx' \
  -d '{"projectId":"project_id","title":"Updated demo","type":"html","html":"<!doctype html><html><body><h1>Updated</h1></body></html>"}'
```

## Install As A Codex Skill

Download `nishare-api.tar.gz`, then install it into your Codex skills directory or import it through your Codex skill installer.

Expected skill name:

```text
nishare-api
```

Typical usage:

```text
Publish this HTML to Nishare and return the shareUrl.
```

## Use With Any AI Tool

Copy the instructions from `AI_TOOLS.md` into the system prompt, custom instructions, project rules, or agent profile of your AI tool.

Recommended prompt:

```text
把当前内容发布到 Nishare，成功后只返回 shareUrl，失败返回 message。
```

English version:

```text
Publish the current content to Nishare. On success, return only the shareUrl. On failure, return the message.
```

## API Summary

Production base URL:

```text
https://nishare.com
```

Endpoints:

| Method | Path | Auth | Purpose |
|---|---|---|---|
| `POST` | `/api/ai/publish` | Optional | Create a new share. |
| `POST` | `/api/ai/update` | Required | Update an existing project. |

Authentication headers:

```http
X-Nishare-Key: nsk_xxx
Authorization: Bearer nsk_xxx
```

Supported content types:

- `html`: full HTML document.
- `markdown`: Markdown document text.
- `image`: image data URL, base64, or image URL.

For all fields, validation rules, response examples, and limits, read [`references/api.md`](references/api.md).

## Good Agent Behavior

When an agent uses Nishare:

- Return the `shareUrl` on success.
- Surface `message` on failure.
- Include `matches` if content review fails.
- Do not wrap HTML in Markdown fences.
- Use the API key only in request headers, never inside generated public content.

## Publishing Directory Fit

This package is suitable for:

- Codex skills
- AI tool prompt directories
- Cursor and editor agent rules
- OpenAI GPT Actions, after adding an OpenAPI schema
- MCP directories, after wrapping the API as an MCP server

See [`PUBLISHING.md`](PUBLISHING.md) for the recommended submission plan.

## License

MIT
