# 13: Core Features You May Not Know Yet

## 1. Lesson Overview

Other ways to start Claude Code from the terminal, and how to get back into an old session. After this you should know the difference between `claude`, `claude "prompt"`, `claude -p`, and `claude -c`.

## 2. Key Concepts

**Starting with a prompt**
- *Simple:* Give your first instruction in the same line that starts Claude Code.
- *Technical:* `claude "prompt"` opens the normal interactive session and immediately begins answering.

**Print mode (`-p`)**
- *Simple:* Ask one question, get the answer, and return to your normal terminal.
- *Technical:* Claude Code does the work in the background without opening the interactive interface, prints the response, and exits.

**Claude Code is not only for editing**
- You can ask it to explain a project, answer questions about code, or discuss possible solutions.

**Resuming sessions**
- *Simple:* Old conversations are saved and can be reopened.
- *Technical:* A resumed session comes back with all of its context.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Interactive mode | The normal back-and-forth session | The default way of working |
| Flag | An option added after a command, like `-p` | Changes how Claude Code starts |
| Resume | Reopen an earlier session with its context | Recovers work after a crash or closed window |

## 5. Examples

```bash
claude                          # start an interactive session
claude "explain this project"   # interactive, starts with this prompt
claude -p "explain this project"  # answer once, then exit
claude -c                       # continue the most recent session
```

Inside Claude Code:

```
/resume
```

Shows your past sessions so you can pick one.

## 6. Important Facts

| Command | Effect |
|---|---|
| `claude "prompt"` | New session with an initial prompt |
| `claude -p "prompt"` | One answer, no ongoing session |
| `claude -c` | Continue the last session |
| `/resume` | Browse and reopen any older session |

Even for a read-only task like "explain this project", Claude Code may still ask permission to explore files.

## 7. Common Beginner Mistakes

- **Mixing up `-p` and `-c`.** `-p` = print and quit. `-c` = continue.
- **Mixing up `-c` and `/resume`.** `-c` goes straight to the *last* session; `/resume` lets you *choose*.
- **Thinking a closed terminal means lost work.** The session can be resumed.

## 8. Connections Between Concepts

Resuming brings back the context described in `lesson-11.md`. It is the opposite of `/clear`: one restores old context, the other discards it.

## 9. Practical Understanding

`claude -p` is handy for quick questions. `claude -c` is the fastest way back to work after an editor crash or a break.

> **Transcript note:** the instructor calls `-c` a "command"; it is a flag added to the `claude` command.
