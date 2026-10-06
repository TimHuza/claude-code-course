# 32: Encouraging Agent Usage

## 1. Lesson Overview

How to make sure Claude Code really uses your custom subagent. After this you should know to put the instruction in `CLAUDE.md` instead of relying on the description alone.

## 2. Key Concepts

**Description = likely; `CLAUDE.md` = almost certain**
- *Simple:* A good description makes use probable. A written rule makes it close to guaranteed.
- *Technical:* `CLAUDE.md` is loaded into every session, so an instruction there applies to every prompt without being repeated.

**Result**
- Claude Code started several instances of the docs explorer in parallel, plus the Explore agent for the codebase. No research ran on the main agent.

## 5. Examples

Rule added to `CLAUDE.md` (reconstructed):

```markdown
Whenever working with any third-party library or similar, you must look up the
official documentation to ensure you're working with up-to-date information.
Use the docs-explorer subagent for efficient documentation lookup.
```

## 6. Important Facts

- The same subagent can run as multiple instances at once.
- Subagents may still ask for permissions (e.g. web search).
- The review found a real problem: a required Better Auth plugin for Next.js was missing in `auth.ts`.

## 7. Common Beginner Mistakes

- **"We can do better than hoping."** Do not rely on automatic discovery for things that must happen.
- **Using AI for every fix.** A one-line fix you understand is cheaper to make by hand.
- **Letting a fix grow.** When asking Claude Code to fix one issue, say "and don't do anything else".

## 8. Connections Between Concepts

Combines `lesson-25.md` (`CLAUDE.md` is always loaded) with `lesson-31.md` (custom subagent), and applies rule 5 from `lesson-23.md` (name the tool explicitly).

## 9. Practical Understanding

Pattern to reuse: build a helper, then write a standing rule in `CLAUDE.md` that says when to use it.

> **Transcript note:** some sentences are cut off, and the plugin is written "next cookies"; it is Better Auth's `nextCookies` plugin.
