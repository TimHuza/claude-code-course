# 37: Iterating On The Demo App

## 1. Lesson Overview

A walkthrough of several prompts in a row, showing the normal working rhythm with Claude Code. The instructor calls this lecture skippable; there are no new features, only the workflow.

## 2. Key Concepts

**Set up first, then build**
- Normally you create `CLAUDE.md`, subagents, and skills at the *start* of a project. The course did it step by step only to explain each feature.

**The iteration loop**
1. Clear the context for a new task.
2. Write the prompt, including pitfalls you already know.
3. Send it in plan mode.
4. Review the plan and add anything you forgot.
5. Accept and let it implement.
6. Test the result yourself.
7. Describe what is wrong and repeat.

**Share what you know**
- The instructor states that route protection should be done per route, because in Next.js doing it through layouts is discouraged. Saying this upfront avoids fixing it later.

**Randomness**
- With AI there is always some randomness. A good setup raises your chances of good results; it does not guarantee them.

## 5. Examples

Prompts used (paraphrased):

- "Redirect the user to `/dashboard` after successful authentication. Protect the dashboard and all note routes, except the public shared-note route. Add protection on a per-route level."
- A multi-step task: note form component, new note route, form submission, saving to the database.
- A follow-up on the plan: "also add a logout button to the header, visible only when authenticated".
- A fix: check the login state on the server before the page is sent, so the logout button does not appear late.
- "Add a toolbar exposing the Tiptap tools listed in `@spec.md`."

## 6. Important Facts

- Mentioning "use modern Next.js features" raises the chance that matching skills are loaded. Such a hint could also live in `CLAUDE.md`.
- The instructor tests manually, e.g. deleting the login cookie in the browser's developer tools to simulate being logged out.

## 7. Common Beginner Mistakes

- **Thinking a different result means a bad prompt.** Results vary between runs.
- **Sending vague bug reports.** The instructor names the cause and the wanted behavior.
- **Skipping your own testing.** Several problems were only found by using the app.

## 8. Connections Between Concepts

Everything from this section in action: `/clear` and `@` (`lesson-22.md`), the rules in `lesson-23.md`, `CLAUDE.md` (`lesson-25.md`), plan mode (`lesson-27.md`), subagents (`lesson-32.md`), and skills (`lesson-34.md`).

> **Transcript note:** "Spack MD" is `spec.md` and "Cloud Code" is Claude Code.
