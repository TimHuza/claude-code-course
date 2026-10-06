# 39: Building & Using Custom Commands (Prompt Templates)

## 1. Lesson Overview

How to save a prompt you use repeatedly as your own slash command. After this you should know where command files go and how arguments work. Read `lesson-38.md` first: this feature is now merged with skills.

## 2. Key Concepts

**Custom command**
- *Simple:* A saved prompt you run by typing `/name`.
- *Technical:* A Markdown file in a `commands` folder. In its simplest form it contains only the prompt text.

**Optional metadata**
- `description` – shown when you browse commands.
- `allowed-tools` – restricts the tools Claude Code may use while running this command.

**Arguments**
- *Simple:* Extra words typed after the command are inserted into the prompt.
- *Technical:* `$ARGUMENTS` in the file is replaced with your input, like parameters of a function.

**Run by you**
- Custom commands are meant to be executed by you, not discovered automatically by Claude Code.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Custom command | A reusable prompt as a slash command | Avoids retyping |
| Prompt template | A prompt with placeholders | One command, several uses |
| Code review | Checking code for problems | The lesson's example use |

## 4. How Things Work

1. Create a Markdown file in `.claude/commands/`.
2. Write the prompt, optionally with metadata and `$ARGUMENTS`.
3. Close Claude Code and start a new session so the command is loaded.
4. Type `/`, choose the command, optionally add arguments, press Enter.

## 5. Examples

```
/code-review bugs,security
```

Claude Code runs the saved prompt with `bugs,security` in place of `$ARGUMENTS`, explores the codebase, and produces a report. The prompt content is the same idea as the skill in `lesson-36.md`.

## 6. Important Facts

- Project commands: `.claude/commands/`. Global commands: the same folder inside the `.claude` folder in your home directory.
- A restart is required after adding a command.
- Tool restrictions apply only to that command's run. Your next prompt has all tools again.

## 7. Common Beginner Mistakes

- **Treating review findings as facts.** Not every finding is a real issue. Decide which to act on.
- **Expecting restrictions to persist.** They end with the command.
- **Forgetting to restart.** The command will not appear.

## 8. Connections Between Concepts

| | Skill (`lesson-34.md`) | Custom command |
|---|---|---|
| Triggered by | Mainly Claude Code | You |
| Folder | `.claude/skills/<name>/SKILL.md` | `.claude/commands/<name>.md` |

## 9. Practical Understanding

After the review the instructor wrote a normal prompt listing the findings to fix and ran it in plan mode. Review with a restricted command, then fix with a regular prompt. Always check AI-written code yourself too.

> **Transcript notes:** ".inf file" is a `.env` file, and "better off" / "off secret" are Better Auth and its auth secret. The command file itself is attached to the course and not shown in the transcript.
