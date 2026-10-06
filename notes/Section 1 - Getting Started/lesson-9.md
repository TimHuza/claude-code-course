# 9: Configuring Claude Code

## 1. Lesson Overview

Where Claude Code's settings live and how to change them. After this you should know the three settings files, which one wins when they disagree, and how to block Claude Code from reading secret files.

## 2. Key Concepts

**Settings levels**
- *Simple:* You can set rules for your whole computer, or just for one project.
- *Technical:* Settings are stored in JSON files named `settings.json`, in a `.claude` folder either in your home directory (global) or in the project (project-specific).

| File | Applies to | Shared with team? |
|---|---|---|
| `~/.claude/settings.json` | All your projects (global) | No |
| `<project>/.claude/settings.json` | This project | Yes (committed to Git) |
| `<project>/.claude/settings.local.json` | This project, only you | No (not in source control) |

**Override order:** `settings.local.json` overrides project `settings.json`, which overrides global settings.

**Permissions setting**
- *Simple:* A list of things Claude Code is allowed or forbidden to do.
- *Technical:* Rules name a **tool** plus an optional restriction on which files it applies to. Key built-in tools: **Read** (read files), **Write** (write files), **Bash** (run terminal commands).

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| `.claude` folder | Folder holding Claude Code's configuration | Where settings files live |
| JSON | A simple text format for structured data | Settings files use it |
| Tool | A built-in ability Claude Code can use | Permissions are written per tool |
| `.env` file | File that usually stores secrets (passwords, API keys) | You typically deny access to it |
| Source control | A system like Git that tracks file history | Decides whether a settings file is shared |
| Tokens | The units of text an AI model processes and you pay for | Some settings (thinking mode) affect token use |

## 4. How Things Work

Changing a setting from inside Claude Code:

1. Run `/config`.
2. Browse the list of settings and their current values.
3. Change one (e.g. the theme, or thinking mode).
4. Claude Code writes the change into the global `settings.json` (the default behavior at recording time).

## 5. Examples

Turning thinking mode off (saves tokens when tasks are simple):

```json
{
  "alwaysThinkingEnabled": false
}
```

Denying access to `.env` files. *Additional knowledge: the transcript describes this rule but does not show its text. It typically looks like this:*

```json
{
  "permissions": {
    "deny": ["Read(**/.env)", "Write(**/.env)"]
  }
}
```

## 6. Important Facts

- `/config` – opens the interactive settings menu.
- `alwaysThinkingEnabled` – turns thinking mode on/off.
- `permissions` – allow/deny rules; **not set by default**, so add it yourself.
- Enterprises can also configure Claude Code for all team members (not covered here).
- The full, current list of settings is in the official docs.

## 7. Common Beginner Mistakes

- **Confusing the two project files.** `settings.json` is for the team; `settings.local.json` is your private override.
- **Assuming secrets are protected by default.** They are not; you must add a deny rule.
- **Denying a whole tool.** You normally do not block Read entirely, only Read on specific files.

## 8. Connections Between Concepts

The permission prompts from `lesson-7.md` are the interactive side of this system; the `permissions` setting is the permanent, written-down side. `lesson-14.md` goes deeper.

## 9. Practical Understanding

In a real project you usually keep personal preferences global, commit shared project rules to `settings.json`, and add a deny rule for secret files before letting Claude Code work.

> **Transcript note:** the instructor describes a Mac setup (`.claude` in the user's home directory). On Windows the equivalent is `C:\Users\<you>\.claude`.
