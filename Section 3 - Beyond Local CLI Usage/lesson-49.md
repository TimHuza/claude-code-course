# 49: Don't forget to configure!

## 1. Lesson Overview

A tour of the desktop app's settings. After this you should know where to find the options that change how Claude Code behaves in the app.

## 2. Key Concepts

**Settings**

| Area | What you find there |
|---|---|
| General | Appearance, font |
| Account | Account management, log out |
| Usage | How much of your plan is left |
| Claude Code | Bypass permissions, worktree location, bring app to foreground when input is needed, preview feature |
| Privacy | What you share with Anthropic |

**Bypass permissions**
- *Simple:* Claude Code never asks before doing anything.
- *Technical:* Even in accept edits mode it normally still asks before deleting something or making a Git commit. With bypass enabled it never asks. Same risk as `--dangerously-skip-permissions` in the CLI.

**Customize**

| Section | Purpose |
|---|---|
| Skills | Manage skills, create one (manually or with Claude's help), browse skills suggested by Anthropic |
| Connectors | Integrations, e.g. GitHub so pull requests can be opened for you |
| Plugins | Manage and install plugins (the equivalent of `/plugin` in the CLI) |

## 6. Important Facts

- Bypass permissions must be enabled in settings before it can be chosen for a session.
- The settings change as the app evolves, so look through them from time to time.

## 7. Common Beginner Mistakes

- **Enabling bypass permissions for convenience.** It means no safety checks at all.
- **Never opening Privacy.** Check you are not sharing data you do not want to share.

## 8. Connections Between Concepts

Same features as the CLI, with a graphical interface: permissions (Section 1, `lesson-14.md`), skills (Section 2, `lesson-34.md`), plugins (Section 2, `lesson-42.md`). Worktrees are explained in `lesson-47.md`.

> **Transcript note:** the transcript says plugins can be installed "through the IDE here"; the desktop app is meant.
