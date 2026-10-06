# 12: When To Start New Sessions & Making Sense of Compaction

## 1. Lesson Overview

What happens when the context window fills up, and why short, focused sessions work better. After this you should know when to compact and when to start fresh.

## 2. Key Concepts

**Compaction loses detail**
- *Simple:* A summary is shorter than the original, so some things are forgotten.
- *Technical:* Claude Code generates a summary of the conversation plus instructions to itself on how to continue. Work does not stop, but details from the earlier conversation are lost.

**Context fills faster than you expect**
- Files Claude Code reads and code it generates also consume tokens, not just your messages.

**One task, one session**
- *Simple:* Start a new session for each new feature.
- *Technical:* Short sessions avoid compaction and keep the context free of unrelated information.

## 4. How Things Work

1. The conversation grows until the context window is nearly full.
2. Claude Code compacts automatically (or you run `/compact`).
3. It continues working from the summary.

## 5. Examples

- About to request a large task in an already long session → run `/compact` first to make room.
- Finished feature A, starting feature B → `/clear` or a new terminal with `claude`.
- Claude Code keeps failing to fix a bug → start a new session and try again.

## 6. Important Facts

- `/compact` – trigger compaction manually.
- `/clear` – start fresh in the same terminal (see `lesson-11.md`).
- Compaction **will** cause information loss.

## 7. Common Beginner Mistakes

- **Confusing `/compact` and `/clear`.** `/compact` keeps a summary and continues the same work. `/clear` throws everything away.
- **Using one endless session for everything.** Quality drops as details get compacted away.
- **Pushing harder when stuck.** A clean session often works better than more messages in a confused one.

## 8. Connections Between Concepts

This applies the context window idea from `lesson-11.md`: because the window is limited, session hygiene matters.

## 9. Practical Understanding

Rule of thumb: same task and need room → `/compact`. New task or stuck → new session.
