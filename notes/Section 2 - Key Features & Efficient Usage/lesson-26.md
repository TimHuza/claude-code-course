# 26: CLAUDE.md vs "Auto Memory"

## 1. Lesson Overview

Claude Code has two ways of remembering things between sessions. After this you should know who maintains each one and when to rely on which.

## 2. Key Concepts

| | `CLAUDE.md` | Auto Memory |
|---|---|---|
| Written by | **You** | **Claude Code**, on its own |
| Contains | Crucial general information and instructions | Things it learned from working with you |
| Location | In your project | `~/.claude/projects/<project>/memory/` |
| Loaded | Every session | Every session (see note below) |

**Auto Memory**
- *Simple:* Claude Code takes its own notes about what you taught it.
- *Technical:* It stores information in a `MEMORY.md` file, and may add topic-specific memory files next to it, per project. It is instructed to keep them concise.

**What it tends to save**
- A mistake you called out several times.
- A code style you corrected it to use.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Auto Memory | Memory written automatically by Claude Code | You need not think of everything yourself |
| `MEMORY.md` | The main auto-memory file | What gets loaded into new sessions |
| `~` | Your user home folder | The memory lives outside the project |

## 6. Important Facts

- Available since Claude Code version 2.1.59.
- `/memory` – enable, disable, and configure Auto Memory; also browse and edit the memory files.
- The first 200 lines of `MEMORY.md` are loaded.

## 7. Common Beginner Mistakes

- **Treating Auto Memory as a replacement for `CLAUDE.md`.** It is an extra help.
- **Hoping Claude Code will memorize an important rule.** If you know a rule should always apply, write it into `CLAUDE.md` yourself.
- **Looking for memory files in the project.** They are in the global `.claude` folder.

## 8. Connections Between Concepts

Extends `lesson-25.md`. Both exist for the same reason: sessions start without knowledge, and both must stay concise because they use context space.

> **Transcript note:** the lesson says Claude loads "the first 200 lines of the `MEMORY.MD` file for every new conversation and the entire memory files for every new session". The difference between "conversation" and "session" is not explained, so this sentence is unclear.
