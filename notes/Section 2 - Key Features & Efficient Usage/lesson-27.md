# 27: Leveraging Plan Mode

## 1. Lesson Overview

Plan mode makes Claude Code research and propose a plan before it changes anything. After this you should know how to enter it, what happens in it, and how to respond to a plan.

## 2. Key Concepts

**Plan mode**
- *Simple:* "Think first, show me the plan, then build."
- *Technical:* In this mode Claude Code has no permission to edit files. It explores the project, may ask clarifying questions, and writes a plan for you to approve.

**Why use it**
- It turns average prompts into good ones, and good prompts into better ones.
- The instructor's default: start in plan mode for the vast majority of tasks, even simple-looking ones.

**Plans are saved**
- Plans are stored locally and temporarily, so Claude Code can still refer to them after the context is cleared.

**Smaller tasks**
- Small, focused tasks tend to give better results. For several tasks at once, run several Claude Code instances in parallel.

## 4. How Things Work

1. Write the prompt.
2. Press `Shift + Tab` until plan mode is active, then send.
3. Claude Code explores and possibly asks questions.
4. It presents the plan with options.
5. You accept, or give feedback. Feedback sends it back to planning to revise.
6. After you accept, it implements.

## 5. Examples

Task (paraphrased): set up the core routes and pages, do **not** implement authentication yet, and put only a dummy message on each page.

Feedback given on the plan:

```
I only want a single /authenticate route which supports only email + password auth
```

## 6. Important Facts

Options offered after a plan (at recording time):

| Option | Meaning |
|---|---|
| Accept, clear context, auto-accept edits | Start nearly empty with only the plan; no edit prompts |
| Accept, keep context, approve edits manually | Continue in the same conversation |
| Give more information | Revise the plan |

- "Clear context" keeps the plan and discards everything before it.
- Even with edits auto-accepted, commands such as linting or building still ask permission.

## 7. Common Beginner Mistakes

- **Skipping plan mode for "easy" tasks.** That is where wrong assumptions slip through.
- **Accepting a plan unread.** The plan is your cheapest chance to correct course.
- **Fearing "clear context" loses the plan.** It does not.

## 8. Connections Between Concepts

Plan mode is the third mode reached with `Shift + Tab`, next to default and accept edits (Section 1, `lesson-14.md`). It supports "Think, Plan, Prompt" from `lesson-23.md`.

## 9. Practical Understanding

Typical loop: prompt in plan mode → read the plan → correct it → accept with cleared context → check the result.

> **Transcript note:** the instructor reads out a further option that sounds identical to the second and says he is unsure what it is for. The option list changes between versions, so yours may differ.
