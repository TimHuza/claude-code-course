# 30: Understanding Subagents

## 1. Lesson Overview

Claude Code can hand parts of a task to helper agents. After this you should understand what a subagent is and why it keeps the main context clean.

## 2. Key Concepts

**Subagent**
- *Simple:* A helper that does one part of the job and reports back.
- *Technical:* A separate agent started by the main agent. It can run in parallel with other work.

**Separate context window**
- *Simple:* The helper uses its own notepad, not yours.
- *Technical:* A subagent has its own context window. Only its result, a summary, is loaded into the main context. This is a key reason the feature exists.

**Built-in subagents**
- Claude Code delegates to built-in subagents automatically. Example: the **Explore** agent, optimized for reading and understanding files and folders.

**Two benefits**
1. Speed, through parallel work.
2. Dedicated experts for specific tasks, without filling the main context.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Main agent | The Claude Code you are talking to | Owns the main context window |
| Subagent | A helper agent with its own context | Offloads work |
| Explore agent | Built-in subagent for reading the codebase | Used automatically |
| Delegate | Hand a task to a subagent | How work gets split |

## 4. How Things Work

1. You send a task.
2. The main agent starts a subagent for part of it (e.g. exploring files).
3. The main agent continues with other work meanwhile.
4. The subagent returns a summary.
5. The main agent uses the summary to answer.

## 5. Examples

The instructor asks for a review: is the implementation in line with the libraries' usage instructions? It is sent in normal mode (not plan mode), because only an answer is wanted. The Explore agent reads the project while the main agent looks up documentation.

## 6. Important Facts

- You can recognize a subagent task because it shows how many tokens it used and how long it took.
- In this demo the documentation lookups still ran step by step on the **main** agent. That is the problem solved in `lesson-31.md`.

## 7. Common Beginner Mistakes

- **Thinking subagents make work free.** They still use tokens; they just keep them out of the main context.
- **Expecting the main agent to know everything the subagent read.** It only receives the summary.
- **Thinking you must set them up.** Built-in ones work out of the box.

## 8. Connections Between Concepts

Subagents address the limited context window from Section 1, `lesson-11.md`: less in the main context means later compaction and fewer lost details.
