# 7: Base Usage & IDE Integration

## 1. Lesson Overview

Your first real task with Claude Code: sending a prompt, watching it work, and approving a file change. It also shows how the VS Code extension adds a visual side to the CLI. After this you should understand the prompt → explore → ask permission → edit cycle.

## 2. Key Concepts

**Prompting**
- *Simple:* You type what you want in plain language.
- *Technical:* Your text is a prompt sent to the AI model. It can be vague for simple tasks and more specific for harder ones.

**Claude Code explores before it edits**
- *Simple:* It looks around your project first.
- *Technical:* In the demo it searched the codebase, recognized a Next.js project (it can work this out from `package.json` on its own), found the `page.tsx` file, read it, then prepared the edit.

**Permission before editing**
- *Simple:* By default it asks before changing a file.
- *Technical:* The default mode does not grant all permissions. Each edit triggers a "Do you want to make this edit?" prompt. More in `lesson-14.md`.

**IDE integration**
- *Simple:* An extension connects Claude Code to your editor.
- *Technical:* The official **Claude Code extension by Anthropic** for VS Code shows proposed changes in VS Code's diff editor and offers a chat panel as an alternative to the terminal.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Prompt | Your instruction to the AI | The main way you control Claude Code |
| IDE | A code editor with extra tools (e.g. VS Code) | Where the integration lives |
| Diff | Side-by-side view of old vs. new code | How you review a change before accepting |
| Extension | An add-on for the editor | Enables the diff view and chat panel |
| Dev server | A local program serving your app while you develop | Lets you see changes in the browser immediately |

## 4. How Things Work

1. Type a prompt and press Enter.
2. Claude Code searches and reads the relevant files.
3. It proposes an edit and asks for permission.
4. You review the diff: **left = original file, right = proposed version**.
5. You choose:
   - **Yes** – allow this one edit.
   - **Yes, allow all edits during this session** – stop being asked for edits (the instructor's usual choice).
   - Reject.
6. Claude Code writes the file and reports what it did.

## 5. Examples

Prompt used in the lesson (paraphrased):

```
Replace the starting page of this Next.js project with a page that says "Hello World" centered in the middle of the screen
```

Opening the chat panel in VS Code: open the command bar, type "Claude Code", choose **Focus Input**.

## 6. Important Facts

- Without the extension, the diff is shown as text in the terminal.
- With the extension, you can accept or reject directly in the editor, or answer in the terminal.
- The VS Code panel lets you attach files, browse past conversations (including terminal ones), and start new ones.
- The course uses the terminal, because it works with every editor.

## 7. Common Beginner Mistakes

- **Thinking the extension *is* Claude Code.** The CLI is the tool; the extension is an optional layer on top.
- **Accepting without reading the diff.** The diff is your chance to catch a wrong change.
- **Thinking "allow all edits" means allow everything.** It covers file edits only, for this session (see `lesson-14.md`).

## 8. Connections Between Concepts

This is the first use of the session started in `lesson-4.md`. The permission prompt here is the simple version of the permission system in `lesson-9.md` and `lesson-14.md`.

## 9. Practical Understanding

Real work follows this loop all day: describe the task, let Claude Code explore, review the diff, approve or reject.

> **Transcript note:** several lines of this transcript are cut off mid-sentence, so a few details (for example the exact wording of the menu options) are reconstructed from context.
