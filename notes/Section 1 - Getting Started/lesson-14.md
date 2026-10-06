# 14: Advanced Permissions Management

## 1. Lesson Overview

How much freedom Claude Code has, and how to give it more. After this you should understand the three levels shown (default, accept edits, skip all permissions) and the risk of each.

## 2. Key Concepts

**Default mode**
- *Simple:* Claude Code asks before changing anything.
- *Technical:* Every file edit and every state-changing command needs your approval.

**Accept edits mode**
- *Simple:* It may edit files in your project without asking.
- *Technical:* Only **file edits inside the project** are auto-approved. Commands that change something (e.g. `git add`, `git commit`, creating a folder) still require permission.

**Per-command approval**
- When asked about a command you can allow it once, or tell Claude Code not to ask again for that specific command. Other commands (e.g. `git restore`) will still trigger a prompt.

**Dangerously skip permissions**
- *Simple:* It never asks. You have no control while it works.
- *Technical:* Started with a flag; every permission request is granted automatically. It could erase Git history or delete files permanently.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Permission mode | The current level of freedom | Decides how often you are interrupted |
| Bash tool | Claude Code's ability to run terminal commands | Most risky actions go through it |
| Git commit | A saved snapshot of your project in Git | The example of a non-edit action |

## 4. How Things Work

Asking for an edit **and** a commit in accept edits mode:

1. Claude Code edits the file without asking.
2. It runs read-only commands (checking Git status and history) to write a good commit message.
3. For `git add` and `git commit`, it stops and asks.
4. You allow once, or allow those commands from now on.

## 5. Examples

```bash
claude --dangerously-skip-permissions
```

You get a warning and must confirm. Then a prompt like "edit X and commit the changes" runs start to finish with no questions.

## 6. Important Facts

| Action | Key / command |
|---|---|
| Switch between modes | `Shift + Tab` |
| Cancel a proposed edit | `Esc` (you can then send a follow-up message) |
| Skip all permissions | `claude --dangerously-skip-permissions` |

## 7. Common Beginner Mistakes

- **Thinking accept edits means "do anything".** It only covers editing files in the project.
- **Thinking "outside my project is safe" in skip mode.** Claude Code could write a script and run it, and that script could affect your whole machine. Unlikely, but possible.
- **Using skip mode without a safety net.** Combine it with a sandbox (`lesson-15.md`, `lesson-16.md`) and Git (`lesson-17.md`).

## 8. Connections Between Concepts

- The edit prompt first appeared in `lesson-7.md`.
- Permanent allow/deny rules live in settings files (`lesson-9.md`); modes here are the in-session equivalent.

## 9. Practical Understanding

More freedom means fewer interruptions but less oversight. Many people use accept edits for normal work and approve commands one by one.

> **Transcript notes:**
> - The instructor says the second option grants the edit permission "permanently". Per `lesson-7.md` that option is "allow all edits during this session", so it is likely session-only.
> - The instructor says Claude Code "still can't access your hard drive outside of your project" in skip mode, and then explains that a script it writes could. Treat the second statement as the real risk.
