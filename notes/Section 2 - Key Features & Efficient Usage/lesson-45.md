# 45: Running Claude Code In A (Ralph) Loop

## 1. Lesson Overview

The Ralph loop runs Claude Code over and over on a task list with no human involved. After this you should understand how it works, what it needs, and its trade-offs.

## 2. Key Concepts

**Ralph loop**
- *Simple:* A script that keeps restarting Claude Code until the to-do list is done.
- *Technical:* A shell script loops up to a maximum number of iterations. Each iteration invokes Claude Code non-interactively with the same prompt. Named after Ralph Wiggum from The Simpsons, for naive persistence.

**The task list**
- A JSON file (`prd.json` in the demo) with tasks. A common convention per task: a description, steps, and a `passes` flag starting at `false`.
- The agent picks a task itself, completes it, and sets `passes` to `true`.
- The format is free, since an AI reads it.

**Self-verification is essential**
- The prompt tells Claude Code to verify changes by running tests and by checking the site in the browser. Without that, nothing catches errors.

**Broad permissions need a sandbox**
- The loop only works if Claude Code never waits for approval, so all permissions are allowed. Therefore sandbox mode **must** be enabled.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Shell script | A file of terminal commands run as a program | It drives the loop |
| Iteration | One pass of the loop | The maximum is the exit condition |
| `passes` flag | Marks whether a task is done | How progress is tracked |
| Vibe coding | Accepting AI output without understanding or reviewing it | The trap to avoid |

## 4. How Things Work

1. Write a spec and derive a task list from it (AI can help; review it).
2. Enable sandbox mode.
3. Run the script with a maximum number of iterations (e.g. 10).
4. Each iteration: Claude Code picks a task where `passes` is `false`, implements it, verifies it, marks it done.
5. The loop ends when all tasks are done or the maximum is reached.
6. You review the overall result.

## 5. Examples

Task list shape, as described in the lesson:

```json
[
  {
    "description": "Users can sign up with email and password",
    "steps": ["Create the form", "Store the user", "Redirect to dashboard"],
    "passes": false
  }
]
```

Watching progress from a second terminal:

```bash
claude -c
```

## 6. Important Facts

- Claude Code is started with `-p` (Section 1, `lesson-13.md`).
- `CLAUDE.md`, skills, and subagents still apply.
- The `claude -c` view is not live; run it again to refresh.
- Tasks should each focus on one main problem: not too granular, not too general.
- Several loops can run in parallel on different projects.

| Advantages | Drawbacks |
|---|---|
| Work continues without you | Can use a lot of tokens quickly |
| Good for prototypes, utilities, internal tools | No plan review, little insight while running |
| | A bad result means the tokens were wasted |
| | It can get stuck and need manual help |

## 7. Common Beginner Mistakes

- **Running it without a sandbox.** With all permissions granted, it could damage your machine.
- **"It works" means "it is ready".** A working app is not a production-ready app; it can contain serious security or performance bugs. Always review before publishing.
- **Skipping the upfront work.** Good plan, good tasks, tests, and the right skills decide the result.

## 8. Connections Between Concepts

Combines skip-permissions and sandboxing (Section 1, `lesson-14.md` and `lesson-16.md`), `-p` and `-c` (Section 1, `lesson-13.md`), the spec (`lesson-22.md`), and both feedback methods (`lesson-43.md`, `lesson-44.md`).

> **Transcript notes:** the transcript writes "Rolf"; the name is **Ralph**. The script is attached to the course and not shown. The instructor used the native sandbox because the Docker sandbox gave him problems with browser use.
