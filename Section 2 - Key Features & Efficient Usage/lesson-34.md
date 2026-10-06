# 34: Adding Custom Skills

## 1. Lesson Overview

How to create a skill: the folder structure, the required fields, and how skills load in stages. After this you should be able to set one up and understand why it stays cheap on context.

## 2. Key Concepts

**Folder structure**
- *Simple:* One folder per skill, with a `SKILL.md` inside.
- *Technical:* `.claude/skills/<skill-name>/SKILL.md`. The `skills` folder name and the `SKILL.md` file name are fixed.

**Required metadata**
- `name` – must equal the skill's folder name.
- `description` – the most important part; it tells Claude Code when the skill applies.

**Loading in stages**
1. Only the name and description of *every* skill are loaded into the context.
2. The body of `SKILL.md` is loaded only when Claude Code decides the skill is relevant.
3. Additional linked documents are loaded only if needed after that.

**Reference files**
- Put rarely needed detail in a `references` folder inside the skill and point to it from `SKILL.md`.

**Injecting messages**
- You can type a message while Claude Code is working or planning. It is not sent immediately; it is injected when there is an opening.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Metadata | The settings block at the top of `SKILL.md` | Controls discovery and behavior |
| Discovery | Claude Code deciding a skill is relevant | Depends on name + description |
| `references` folder | Convention for extra skill documents | Keeps `SKILL.md` short |

## 4. How Things Work

1. Create `.claude/skills/`.
2. Add a folder named after the skill.
3. Add `SKILL.md` with `name` and `description`.
4. Write the guidance below the metadata, concisely.
5. Move special-case detail into `references/` and mention the file in `SKILL.md`.

## 5. Examples

```
.claude/skills/
└── modern-best-practice-react-components/
    ├── SKILL.md
    └── references/
        └── you-dont-need-useeffect.md
```

```markdown
---
name: modern-best-practice-react-components
description: Build clean, modern React components that apply common best practices and avoid common pitfalls.
---

...conventions and patterns...

When working with useEffect, read references/you-dont-need-useeffect.md
```

## 6. Important Facts

Optional metadata:

| Field | Effect |
|---|---|
| `allowed-tools` | Restrict tools while the skill is used (default: all) |
| `model` | Model to use with the skill |
| `context: fork` | Run the skill in a new context window instead of the current one |

- Global skills go in the `skills` folder inside the `.claude` folder in your home directory.
- The instructor prefers **project** skills: different projects use different tech stacks, and even an irrelevant skill's name and description use context and might be applied wrongly.

## 7. Common Beginner Mistakes

- **Name not matching the folder.** They must be identical.
- **Thinking skills cost nothing.** Once loaded, a skill occupies context, so keep it concise.
- **Assuming a skill was used.** Claude Code decides; you get no guarantee. Mentioning related terms in the prompt (e.g. "use modern JSX and Tailwind") raises the chance.

## 8. Connections Between Concepts

Same pattern as subagents (`lesson-31.md`): a folder in `.claude`, a Markdown file, and a description that drives automatic use. Unlike `CLAUDE.md` (`lesson-25.md`), a skill is not always loaded.

## 9. Practical Understanding

Write a skill for knowledge that matters for *some* tasks: coding conventions for a framework, a library's pitfalls, your team's patterns.

> **Transcript notes:** the transcript writes the file as "Skill.md"; `lesson-36.md` shows it as `SKILL.md`. It also refers to the skill's "title", which is the `name` field. The reference file's exact name is transcribed as "YouDon'tNeedUseEffect.md".
