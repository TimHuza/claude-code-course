# 22: Prompt Engineering In Action & Working with Specs

## 1. Lesson Overview

The first real prompt of the project: creating a specification document and having Claude Code improve it. After this you should know how to point Claude Code at a file and how to add outside information to a prompt.

## 2. Key Concepts

**Specification document (spec)**
- *Simple:* A written description of the app you are building.
- *Technical:* A document covering features, tech stack, and data structure. Useful for new *and* existing projects. It is a one-time task, not something you do before every prompt.

**Pointing at files with `@`**
- *Simple:* Type `@` and a file name to say "look at this file".
- *Technical:* `@file` is the official way to include a specific file in the context.

**Context is more than files**
- You can paste in other relevant material, such as a documentation article.

**XML tags around pasted text**
- *Simple:* Labels that mark where pasted text begins and ends.
- *Technical:* Wrapping long pasted content in tags helps the model separate it from your instructions. Optional, but the instructor finds it helps.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Spec | Description of what you are building | Gives Claude Code the big picture |
| `@` mention | Reference to a file in a prompt | Puts the right file into context |
| Tech stack | The technologies a project uses | Stops Claude Code guessing |
| Markdown | Simple text formatting (`.md` files) | Format used for the spec |

## 4. How Things Work

1. Describe the app to an AI (the instructor used ChatGPT) and ask for a technical specification.
2. Save it in the project as `spec.md`.
3. Ask Claude Code to format it and fix known problems, pasting in the relevant documentation.
4. Read the result yourself and correct anything that is wrong.

## 5. Examples

The lesson's prompt, reconstructed:

```
We're building an app described in @spec.md

Please format this file as proper Markdown.

Also update the part about the users table and auth-related tables.
We're using the Better Auth library, which expects a certain database schema.

<docs>
...pasted documentation article...
</docs>
```

The demo app: a note-taking app with a rich text editor, where users create, view, edit, delete, and publicly share notes.

## 6. Important Facts

- `spec.md` is the instructor's own choice. Claude Code does **not** expect or require a file with this name.
- `Shift + Tab` before sending switches to accept edits mode (Section 1, `lesson-14.md`).
- Many documentation sites offer a "copy as Markdown" option, which gives cleaner text than copying the whole page.
- Claude Code can find useful files on its own; forgetting to mention one is not a problem.

## 7. Common Beginner Mistakes

- **Referencing every file that might be relevant.** Point only at files you *know* matter.
- **Trusting the AI-written spec blindly.** In the demo it described a `users` table that did not match what the auth library needs.
- **Thinking `spec.md` is a special Claude Code file.** That role belongs to `CLAUDE.md` (see `lesson-25.md`).

## 8. Connections Between Concepts

This applies the two ingredients from `lesson-21.md`: instructions (format, update) plus context (`@spec.md`, pasted docs).

## 9. Practical Understanding

On any project, give Claude Code a description of what it is working on, and feed it the exact documentation you know it will need.

> **Transcript notes:** the auto-generated transcript writes "betterauth" for **Better Auth** and "tictac" for the **Tiptap** editor library. The exact tag name used in the prompt is not shown; `<docs>` above is illustrative.
