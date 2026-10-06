# 25: Crafting Great CLAUDE.MD Files

## 1. Lesson Overview

What `CLAUDE.md` is and what belongs in it. After this you should understand it as Claude Code's long-term memory for a project.

## 2. Key Concepts

**`CLAUDE.md`**
- *Simple:* A note that Claude Code reads at the start of every session.
- *Technical:* A Markdown file in the project root whose content is automatically loaded into every new session, and again after `/clear`.

**What to put in it**
- General rules and information that apply to nearly every prompt, such as which tools to use and the overall architecture.

**Keep it small**
- It is loaded every time, so every line takes context space in every session. A large file pollutes the context.

**Nested `CLAUDE.md` files**
- *Simple:* Extra instruction files for specific folders.
- *Technical:* A `CLAUDE.md` in a subfolder is loaded only when Claude Code works on files in that folder. Any depth of nesting is allowed.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| `CLAUDE.md` | Always-loaded project instructions | Carries knowledge across sessions |
| Root folder | The top folder of the project | Where the main file lives |
| Long-term memory | Information that survives between sessions | Sessions otherwise start with no knowledge |

## 5. Examples

Lines the instructor adds (paraphrased):

```markdown
We're building the app described in @spec.md. Read that file for general
architectural tasks or to double-check the database structure, tech stack
or application architecture.

Keep your replies short. No long explanations with lots of code snippets.
```

Other content in the file: use Bun to run this project's scripts.

## 6. Important Facts

- Location: project root, plus optional copies in subfolders.
- Created by `/init` (`lesson-24.md`), then edited by you.
- Short replies save tokens and keep the context cleaner in long conversations.
- A hint about *when* to read a large file stops Claude Code reading it every time.

## 7. Common Beginner Mistakes

- **Putting everything in it.** Only things relevant to almost every task belong there.
- **Confusing it with the spec.** The spec describes the app in detail; `CLAUDE.md` is short and points to the spec.
- **Expecting nested files to always load.** They load only for work in their folder.
- **Leaving the `/init` version untouched.** It is a starting point to refine.

## 8. Connections Between Concepts

A session forgets everything when cleared (Section 1, `lesson-11.md`); `CLAUDE.md` is what survives. The automatic counterpart is Auto Memory (`lesson-26.md`).

## 9. Practical Understanding

Whenever you find yourself repeating an instruction in several prompts, move it into `CLAUDE.md`.

> **Transcript note:** the instructor also changes the scripts in `package.json` to run with `bun run --bun`, so the Bun runtime is used. This is specific to the demo project.
