# 35: Using Agent Skills as Commands

## 1. Lesson Overview

Every skill you create also appears as a slash command. After this you should understand why, and when running a skill manually makes sense.

## 2. Key Concepts

**Skills appear in the `/` menu**
- *Simple:* Type `/` and your skills are listed next to the built-in commands.
- *Technical:* A skill named `bun-instead-of-node` becomes `/bun-instead-of-node`.

**Primary use is automatic**
- Skills are mainly meant to be discovered and used by Claude Code, not invoked by you.

**What happens when you invoke one**
- It depends on the skill's content. A pure knowledge skill gives Claude Code nothing to *do*, so it replies that it does not know what you want.
- A skill containing instructions or scripts does something useful when invoked.

## 5. Examples

```
/bun-instead-of-node
```

Result in the demo: Claude Code starts, then reports it is unsure what to do, because the skill only states that the project uses Bun instead of Node.js.

## 6. Important Facts

Built-in commands mentioned: `/init`, `/config`, `/clear`.

## 7. Common Beginner Mistakes

- **Thinking you must run skills manually.** No; Claude Code loads them when relevant.
- **Expecting a knowledge skill to act like a command.** It has no task in it.

## 8. Connections Between Concepts

Skills (`lesson-34.md`) and slash commands share one mechanism. Commands meant to be run by you are covered in `lesson-39.md`, and controlling who may invoke a skill is in `lesson-36.md`.
