# 17: Undoing Actions & The Importance of Version Control Systems

## 1. Lesson Overview

What to do when Claude Code makes a change you do not want. After this you should know the two ways to undo (Git and rewind) and why Git is the one to rely on.

## 2. Key Concepts

**Version control (Git)**
- *Simple:* A history of your project that lets you go back to earlier states.
- *Technical:* You save snapshots called commits. Commit frequently so there is always a recent good state to restore.
- More important than ever with AI, because AI can break your codebase or delete files you wanted to keep.
- Bonus: your editor's version control diff view shows exactly what the AI changed in each file.

**Rewind**
- *Simple:* Claude Code's own undo.
- *Technical:* It restores the code to an earlier point in the conversation. It does **not** replace version control.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Version control system | Tool that tracks file changes over time | Your reliable safety net |
| Commit | A saved snapshot in Git | A point you can return to |
| Rewind | Claude Code's built-in undo | Quick, but less reliable |
| Anti-pattern | A common but poor way of writing code | AI output can work and still be poor quality |

## 4. How Things Work

Rewinding:

1. Press `Esc` twice (or run `/rewind`).
2. Claude Code offers points to restore to (for example, the beginning of the conversation).
3. Choose one; the code should return to that state.

## 5. Examples

In the demo, Claude Code added an incrementing counter to the homepage. The instructor then rewound to the beginning of the conversation.

## 6. Important Facts

- `Esc` + `Esc` – open rewind.
- `/rewind` – same feature as a command.
- At recording time, rewind was **buggy** for the instructor: it reported success, but the counter code was still there (visible in version control as an uncommitted change).

## 7. Common Beginner Mistakes

- **Relying on rewind alone.** It may fail. Git is the dependable option.
- **Committing rarely.** Without a recent commit there is nothing good to go back to.
- **Assuming working code is good code.** The instructor notes the generated counter used an anti-pattern. Review what the AI writes.

## 8. Connections Between Concepts

Git is the safety net behind the freer permission modes in `lesson-14.md`. Sandboxes (`lesson-15.md`, `lesson-16.md`) protect your computer; Git protects your project.

## 9. Practical Understanding

Commit before giving Claude Code a bigger task. If the result is bad, try rewind, then check with Git that the change is really gone, and restore with Git if it is not.

> **Transcript note:** the instructor does not explain what the counter anti-pattern is, and the explanation of what `/rewind` lists is cut off.
