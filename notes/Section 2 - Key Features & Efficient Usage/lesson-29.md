# 29: Using MCP Servers & More On Permissions

## 1. Lesson Overview

How to give Claude Code extra tools through MCP servers, using a documentation server as the example. After this you should know what MCP is, how a server is added, and how to add a note when answering a permission prompt.

## 2. Key Concepts

**MCP (Model Context Protocol)**
- *Simple:* A standard way to plug extra tools into AI tools.
- *Technical:* A standard for exposing tools and resources to AI tools such as Claude Code. Claude Code uses them when it needs to, or when you tell it to.

**Context7**
- *Simple:* A tool that fetches official library documentation.
- *Technical:* An MCP server that makes browsing library docs much easier for Claude Code. Free to use at recording time; a paid API key gives higher limits.

**Scope**
- By default a server is installed locally. Adding `--scope user` installs it globally, for all your projects.

**Adding a note to a permission answer**
- When allowing or declining a request, press `Tab` to add extra information, such as the reason.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| MCP server | A program providing extra tools to Claude Code | Extends what it can do |
| Scope | Where something is installed (project or user) | Decides which projects can use it |
| API key | A secret code identifying you to a service | Optional for Context7 |

## 4. How Things Work

1. Copy the install command from the server's page (remove the API key part for free use).
2. Run it in a normal terminal.
3. Restart Claude Code so it sees the server.
4. Check with `/mcp`.
5. Mention the tool in your prompt.
6. Approve its first use.

## 5. Examples

Prompt addition:

```
Use web search or the Context7 MCP to find relevant documentation.
```

Declining with a reason (after pressing `Tab`):

```
I'll run the dev server myself. Just check for TypeScript, linting and build errors.
```

## 6. Important Facts

- `/mcp` – list installed MCP servers.
- `--scope user` – install an MCP server globally.
- `Ctrl + C` twice – exit Claude Code.
- `Tab` on a permission prompt – add extra information.
- First use of an MCP tool asks for permission; you can choose not to be asked again.

## 7. Common Beginner Mistakes

- **Thinking MCP replaces pasting docs.** If you know exactly which article is needed, pasting it remains the safest option.
- **Forgetting to restart.** A running session does not see a newly added server.
- **Installing without mentioning.** Tell Claude Code to use the tool.

## 8. Connections Between Concepts

MCP tools also take space in the context window (Section 1, `lesson-11.md`). The good plan in this lesson came from three things together: plan mode (`lesson-27.md`), clear instructions, and the right tools.

## 9. Practical Understanding

Use Context7 or web search when you do not know which documentation pages are relevant and do not want to look them up.

> **Transcript notes:** the exact install command is not in the transcript (it is on the linked GitHub page). The instructor also saw display glitches in the terminal, which were not related to MCP.
