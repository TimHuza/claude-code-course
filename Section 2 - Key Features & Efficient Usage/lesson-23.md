# 23: Prompt & Context Engineering Recommendations

## 1. Lesson Overview

Five best practices for writing prompts. After this you should have a checklist to run through before sending a prompt.

## 2. Key Concepts

**1. Concise and precise**
Describe the task clearly and accurately, but leave out details and filler that do not matter.

**2. No unnecessary context**
Reference files you *know* matter, not ones you *think* might. The same goes for documentation or any other information.

**3. Think, plan, prompt**
Do not start typing and "fix things over time". Think first, make a plan, then write the prompt. Needing many follow-ups and clarifications is a sign you should plan more upfront, even when using plan mode.

**4. Don't "test" the AI**
If you know about a difficulty, pitfall, or common mistake in the task, say so in the first prompt, together with the recommended solution.

**5. Explicitly name the tools to use**
If a certain tool or feature should be used, tell Claude Code. Do not hope it picks the right one just because it could.

**The common theme:** you are in control; you steer the AI.

## 5. Examples

| Weak | Better |
|---|---|
| "Add auth." | "Add email + password auth with Better Auth. Use one `/authenticate` route. No password reset." |
| `@` six files that might be related | `@` the one file you know must change |
| Staying silent about a known pitfall | "Protect routes per route, not via layouts." |
| Hoping docs get looked up | "Use web search to find the relevant documentation." |

## 6. Important Facts

- Use plan mode for every task that is not trivial (see `lesson-27.md`).
- Tools can be built in (Bash, web requests) or come from MCP servers (`lesson-29.md`). Subagents (`lesson-30.md`) and skills (`lesson-33.md`) can be named in prompts the same way.

## 7. Common Beginner Mistakes

- **Confusing concise with vague.** Short is good only if the task is still described clearly.
- **Treating the AI as a quiz candidate.** Watching it fail costs you time and tokens.
- **Assuming plan mode replaces thinking.** It supports your planning, it does not do it for you.

## 8. Connections Between Concepts

These rules extend `lesson-21.md` and `lesson-22.md`. The instructor applies them repeatedly later, for example the "per route, not layouts" hint in `lesson-37.md`.
