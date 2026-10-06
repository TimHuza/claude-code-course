# 28: Using Claude Code's Built-in Tools

## 1. Lesson Overview

How to make sure Claude Code works from correct, current documentation. After this you should know the ways to supply documentation and that Claude Code can browse and search the web itself.

## 2. Key Concepts

**The problem**
- A task like "implement authentication and database access" depends on rules specific to the libraries involved. Without those rules, Claude Code may set things up incorrectly.

**Ways to supply the knowledge**

| Option | How | Trade-off |
|---|---|---|
| Paste the documentation | Copy the article into the prompt | Most reliable, but you must find it |
| Give links | Tell it to visit specific pages | It has to actually follow them |
| Web search | Tell it to search for the docs | Least effort, least control |
| MCP server | Add a documentation tool | See `lesson-29.md` |

**Built-in web tools**
- Claude Code can visit websites and perform web searches without anything extra installed.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Built-in tool | An ability Claude Code has out of the box | No setup needed |
| Web search | Searching the internet for information | Finds docs you did not provide |
| Documentation (docs) | Official usage instructions for a library | The source of correct setup rules |

## 5. Examples

```
Implement authentication and database access as described in @spec.md.
Use web search to find the relevant documentation.
```

## 6. Important Facts

- Because `CLAUDE.md` points at `spec.md` (`lesson-25.md`), Claude Code should find the spec on its own. Adding `@spec.md` anyway "never hurts" when you know it is needed.

## 7. Common Beginner Mistakes

- **Assuming the AI knows the library's current rules.** Its knowledge may be outdated or incomplete.
- **Hoping it will look things up.** Say so explicitly (rule 5 in `lesson-23.md`).

## 8. Connections Between Concepts

This is context engineering (`lesson-21.md`) applied to documentation. The next lesson adds a dedicated tool for it.

> **Transcript note:** the transcript writes "DEI" where "the AI" is meant, and a few sentences are cut off.
