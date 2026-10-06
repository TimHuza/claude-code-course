# 31: Creating & Using A Custom Subagent

## 1. Lesson Overview

How to build your own subagent, using a documentation explorer as the example. After this you should know where the file goes and what it contains.

## 2. Key Concepts

**Why a custom subagent**
- Reading documentation puts a lot of text into the main context and takes time. A dedicated subagent does it in its own context instead.

**A subagent is a Markdown file**
- *Simple:* One text file describing the helper.
- *Technical:* A `.md` file in an `agents` folder, with settings at the top and plain-language instructions below.

**Parts of the file**

| Part | Purpose |
|---|---|
| `name` | The agent's name (the instructor matches the file name) |
| `description` | Tells Claude Code *when* to use this agent |
| `tools` | Which tools the agent may use |
| `model` | Which model runs it |
| Body | How the agent should work, in normal language |

**Choosing the model**
- Easy tasks do not need the smartest model. Options at recording time: Opus (most capable), Sonnet (middle), Haiku (cheapest). The instructor picks Sonnet.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Custom subagent | A subagent you define | Tailored to your workflow |
| `agents` folder | Where subagent files live | The name is fixed |
| `llms.txt` | An AI-friendly page many websites offer | Cleaner than a normal web page |

## 4. How Things Work

1. Create `.claude/agents/` in your project.
2. Add a Markdown file, e.g. `docs-explorer.md`.
3. Fill in name, description, tools, and model.
4. Describe the behavior in plain language.
5. Start a new session.

## 5. Examples

Illustrative shape (the real file is attached to the course, not shown in the transcript):

```markdown
---
name: docs-explorer
description: Looks up documentation for libraries, frameworks and similar tools.
model: sonnet
---

You are a documentation specialist. Run all lookups in parallel.
Use the Context7 MCP as the primary source and fall back to web search.
When searching the web, look for llms.txt or Markdown versions of pages first.
```

## 6. Important Facts

- Project agents: `.claude/agents/` (the folder **must** be named `agents`).
- Global agents: the `agents` folder inside the `.claude` folder in your home directory, available in all projects.
- The file name is your choice, but it must be a Markdown file.
- The official docs list all tools you can give a subagent.

## 7. Common Beginner Mistakes

- **Writing a vague description.** The description is how Claude Code decides to delegate.
- **Using the most powerful model everywhere.** It costs more with no benefit for simple work.
- **Thinking the body must be technical.** It is plain instructions.

## 8. Connections Between Concepts

Builds on `lesson-30.md` (subagents) and uses the Context7 server from `lesson-29.md`. Whether it actually gets used is handled in `lesson-32.md`.

> **Transcript notes:** the instructor adds a tool he calls "mcp-search" so the agent can load MCP tools dynamically; check the official tool list for the current name. He also notes that such an agent may be built in by the time you watch.
