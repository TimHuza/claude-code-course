# 11: Understanding Sessions & Context

## 1. Lesson Overview

What a session is, what the context window is, and the slash commands for managing them. After this you should understand that Claude Code's memory is limited and belongs to one session.

## 2. Key Concepts

**Session**
- *Simple:* One conversation with Claude Code.
- *Technical:* Each session has its own context. A new session knows nothing about previous ones.

**Context window**
- *Simple:* The AI's short-term memory for the current session. It has a fixed size.
- *Technical:* Measured in tokens. In the demo, the Opus model had 200,000 tokens, and about 20,000 were used before typing anything.

**What fills the context before you start**
- **System prompt** – built-in instructions written by Anthropic.
- **System tools** – descriptions of the built-in tools, so the model knows when to use which.
- **MCP tools** – descriptions of tools from added MCP servers (covered later in the course).
- **Auto-compact buffer** – reserved space you cannot use.

**Compaction**
- *Simple:* When memory fills up, Claude Code replaces the long history with a summary.
- *Technical:* It summarizes the work done and the work remaining, discards the old context, and continues from the summary. Creating the summary costs tokens, which is why the buffer is reserved. Details in `lesson-12.md`.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Context window | Everything the model can "see" at once | When it is full, details get lost |
| Token | Unit of text the model processes | Context size and usage are counted in tokens |
| System prompt | Hidden built-in instructions | Uses context from the start |
| Compaction | Summarizing the conversation to free space | Keeps long sessions running |

## 4. How Things Work

1. You start a session; some context is already used.
2. Every prompt, answer, and file read adds to the context.
3. Near the limit, Claude Code auto-compacts.
4. `/clear` empties the conversation and context so you start fresh.

## 6. Important Facts

- `/clear` – clears the conversation and the context window.
- `/context` – shows how the context window is currently used.
- `/usage` – shows remaining usage on your plan.
- Type `/` to see available commands. They change over time.
- You can run **several sessions in parallel**, even on the same project, by opening another terminal and running `claude`.

## 7. Common Beginner Mistakes

- **Expecting a new session to remember the old one.** It does not.
- **Thinking an empty session has an empty context.** Part is always pre-filled.
- **Confusing `/context` with `/usage`.** `/context` = memory of this session. `/usage` = how much of your subscription allowance is left.
- **Letting parallel sessions edit the same file.** They can work against each other.

## 8. Connections Between Concepts

The 200,000-token figure belongs to the model chosen in `lesson-10.md`. When to clear versus compact is in `lesson-12.md`.

## 9. Practical Understanding

Use `/clear` when you switch to a different task or when Claude Code is stuck. Check `/context` when a session has been running long.

> **Note:** the token numbers reflect the time of recording and may differ now. Run `/context` to see your own.
