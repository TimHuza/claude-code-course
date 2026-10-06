# 16: Using Claude Code's Native Sandboxing

## 1. Lesson Overview

Claude Code has its own sandbox mode, so you do not need Docker. After this you should know how to turn it on and what it restricts.

## 2. Key Concepts

**Native sandbox**
- *Simple:* A safety boundary built into Claude Code.
- *Technical:* It does two things:
  1. **Scopes file access** to the project folder.
  2. **Controls network access**, to prevent exfiltration (data from your project being sent out).

**Why use it instead of Docker**
- You do not have or want Docker.
- Some features may not work well inside the Docker sandbox. The instructor consistently had problems with Claude Code using the browser there.

**Sandbox modes**
- **Auto allow** – the instructor's choice; the idea is fewer prompts because the sandbox already limits what can happen.
- **Regular permissions** – sandboxed, but still asking as usual.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Native | Built into the tool itself | No extra software needed |
| Exfiltration | Data being sent out without your consent | What the network control prevents |

## 4. How Things Work

1. Inside a session, run `/sandbox`.
2. Choose a mode.
3. Claude Code adds a sandbox entry to your settings file (creating the file if needed).
4. All future sessions run sandboxed.

## 6. Important Facts

- `/sandbox` – enable and configure the native sandbox.
- The setting is stored in a settings file (see `lesson-9.md`) and can also be added manually.
- It can be combined with `--dangerously-skip-permissions` for hands-off work with a safety boundary.
- The instructor does **not** use skip-permissions in this course, preferring to approve actions to catch Claude Code heading in the wrong direction.

## 7. Common Beginner Mistakes

- **Thinking it applies to one session only.** It is saved in settings and affects future sessions.
- **Thinking permission prompts are only about safety.** They also let you stop a wrong approach early.

## 8. Connections Between Concepts

| | Docker sandbox (`lesson-15.md`) | Native sandbox |
|---|---|---|
| Needs Docker | Yes | No |
| Enabled by | Starting through Docker | `/sandbox` |
| Extra login | Yes | No |

Both make the skip-permissions mode from `lesson-14.md` safer.

## 9. Practical Understanding

For a hands-off style, enable the sandbox and skip permissions. For close control, keep approving manually. It is a personal preference.

> **Transcript note:** the transcript does not say which settings file is updated, and it does not explain the two modes in detail.
