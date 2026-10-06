# 36: Enhancing Skills & Adding Third-Party Skills

## 1. Lesson Overview

How to tune your skills so they get used correctly, and how to install skills written by others. After this you should know the key metadata options and the install command.

## 2. Key Concepts

**Skill not being used? Fix the description**
- The name and description are all Claude Code sees before loading a skill. Add explicit trigger wording.

**Controlling who can invoke a skill**

| Setting | Effect |
|---|---|
| (default) | Claude Code and you can both use it |
| `disable-model-invocation: true` | Only you, as a slash command |
| `user-invocable: false` | Only Claude Code, automatically |

**Restricting tools**
- `allowed-tools: Read` lets Claude Code read files but not edit or create them while the skill runs.

**Arguments**
- *Simple:* A blank in the skill that is filled with what you type after the command.
- *Technical:* The `$ARGUMENTS` placeholder is replaced by your input.

**Third-party skills**
- Ready-made skills can be installed from public repositories such as skills.sh (free).

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Invocation | Triggering a skill | Can be automatic, manual, or both |
| `$ARGUMENTS` | Placeholder for your input | Makes one skill flexible |
| Third-party | Made by someone else | Saves you writing it |
| `npx` | A tool that comes with Node.js for running packages | Needed for the install command |

## 5. Examples

Trigger wording for a description:

```
Gets triggered when writing ANY kind of CSS code
```

A command-style skill, `.claude/skills/code-review/SKILL.md` (shortened):

```markdown
---
name: code-review
description: Review code for bugs, security or performance issues. Use this skill when asked to perform code reviews or after finishing major tasks.
allowed-tools: Read
---

MODE: $ARGUMENTS

- MODE == BUGS: Focus ONLY on logical or other bugs.
- MODE == SECURITY: Focus ONLY on security issues.
- MODE == PERFORMANCE: Focus ONLY on performance issues.

If MODE is anything else or empty, perform a thorough, general code review.
```

Used as `/code-review BUGS,SECURITY`.

Installing a third-party skill:

```bash
npx skills add <owner/repo>
```

## 6. Important Facts

- Metadata fields: `name`, `description`, `allowed-tools`, `disable-model-invocation`, `user-invocable`.
- `npx skills add` requires Node.js.
- Installed skills are just files: read them, adjust them, or remove parts.

## 7. Common Beginner Mistakes

- **Mixing up the two invocation settings.** `disable-model-invocation` blocks Claude Code; `user-invocable: false` blocks you.
- **Installing third-party skills unread.** They become instructions Claude Code follows, so check what they say.

## 8. Connections Between Concepts

Builds on `lesson-34.md` (creating skills) and `lesson-35.md` (skills as commands). A skill with `$ARGUMENTS` does the job of a custom command (`lesson-39.md`).

> **Transcript notes:** the lesson's example lists `description` twice in the metadata, which looks like a mistake (the version above keeps one). It also says "title + description", while the actual field is `name`. One mode line uses a single `=`, a harmless typo.
