# 33: Introducing Agent Skills

## 1. Lesson Overview

Introduces agent skills: extra knowledge that Claude Code loads only when a task needs it. After this you should know what a skill consists of.

## 2. Key Concepts

**Agent skill**
- *Simple:* A guide Claude Code picks up only when it is relevant.
- *Technical:* Dynamically loaded pieces of context for certain tasks, for example best practices for building React components or Python classes.

**What a skill is made of**
- A `SKILL.md` file (**always required**).
- Optional extra documents or folders of documents.
- Optional scripts the AI may execute (e.g. a cleanup script in Python or JavaScript).
- Optional assets such as images with diagrams.

**Open standard**
- Skills are not exclusive to Claude Code. Other AI coding tools (the lesson names Cursor and OpenCode) support them too.

**Knowledge skills**
- In the instructor's experience, the most useful skills simply provide information, instructions, and best practices.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Agent skill | On-demand knowledge package | Adds expertise without always using context |
| `SKILL.md` | The required main file of a skill | Without it there is no skill |
| Dynamically loaded | Loaded only when needed | Saves context space |

## 7. Common Beginner Mistakes

- **Confusing skills with `CLAUDE.md`.** `CLAUDE.md` is always loaded; a skill is loaded when relevant.
- **Thinking skills must contain code.** Most useful ones are just text.

## 8. Connections Between Concepts

| | Subagent (`lesson-30.md`) | Skill |
|---|---|---|
| What it is | A helper that *does* work | Knowledge *used* during work |
| Context | Its own | Loaded into the current one |

Building one follows in `lesson-34.md`.
