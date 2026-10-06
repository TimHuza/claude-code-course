# 24: Initializing Claude Projects

## 1. Lesson Overview

Two preparation steps before real work starts: do by hand what you already know how to do, then run `/init` so Claude Code learns the project. After this you should know what `/init` does and when to run it.

## 2. Key Concepts

**Do known things yourself**
- *Simple:* If you know exactly how something should be done, just do it.
- *Technical:* The instructor installs packages manually. When AI installs them it sometimes edits the dependency file (`package.json`) directly and inserts outdated version numbers.

**`/init`**
- *Simple:* Claude Code studies your project and writes notes about it.
- *Technical:* It analyzes the codebase (files, folders, installed dependencies, documents such as `spec.md`) and creates a `CLAUDE.md` file from what it found.

**"New project" means new to Claude Code**
- Run `/init` in any project where you have not used Claude Code before, including an existing codebase.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Package / dependency | Reusable code your project installs | Wrong versions cause errors |
| `package.json` | File listing a JavaScript project's dependencies | Where AI may write outdated versions |
| `/init` | Command that analyzes the project | Creates `CLAUDE.md` |
| `CLAUDE.md` | Project instruction file for Claude Code | Explained in `lesson-25.md` |

## 4. How Things Work

1. Install the packages you know you need (the instructor uses `bun add`).
2. Start a **new session** to drop old context.
3. Run `/init`.
4. Approve its requests to explore folders.
5. Review the `CLAUDE.md` it creates.

## 6. Important Facts

- `/init` – analyze the project and create `CLAUDE.md`.
- Packages installed in the demo: Better Auth (login), Zod (validating user input), the Tiptap editor packages, and `bun-types` as a development-only dependency (avoids TypeScript errors).

## 7. Common Beginner Mistakes

- **Letting the AI do everything.** Your own knowledge is faster and more reliable for things you already know.
- **Running `/init` before setup.** Install dependencies first, so `/init` sees the real project.

## 8. Connections Between Concepts

The new session applies the "fresh context for a new task" rule from Section 1, `lesson-12.md`. `/init` finds the `spec.md` from `lesson-22.md`.

> **Transcript notes:** "sod" is the **Zod** library, and "Cloud.md" / "Cloud Code" are **CLAUDE.md** / **Claude Code**.
