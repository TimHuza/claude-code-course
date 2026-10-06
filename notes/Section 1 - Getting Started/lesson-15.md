# 15: Running Claude Code via Docker Sandboxes

## 1. Lesson Overview

A safer way to let Claude Code run without permission prompts: put it inside a Docker sandbox. After this you should understand what a sandbox protects and what it does not.

## 2. Key Concepts

**Sandbox**
- *Simple:* A sealed box on your computer. Whatever runs inside cannot reach the rest of your machine.
- *Technical:* Docker's sandbox feature creates an isolated environment on the fly, wraps your local project in it, and starts Claude Code inside.

**Skip-permissions by default inside the sandbox**
- *Simple:* Because the box limits the damage, Claude Code is allowed to work without asking.
- *Technical:* It starts in bypass-permissions mode. Even a script that tried to erase the hard drive could not leave the sandbox.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Docker | Software that runs programs in isolated environments | Required for this approach |
| Sandbox | An isolated environment with restricted access | Limits the damage Claude Code could do |
| Bypass permissions | The mode where nothing is asked | The default inside the Docker sandbox |

## 4. How Things Work

1. Have Docker installed and running.
2. Start Claude Code through Docker's sandbox feature, in your project folder.
3. Docker creates the sandbox and wraps your project in it.
4. Log in / set up Claude Code again (the sandbox is a brand-new system to it).
5. Work as usual: it can edit files and commit, but only inside the project.

## 5. Examples

```bash
docker sandbox run claude
```

The command is named at the start of `lesson-16.md`; this lesson's transcript only describes it.

## 6. Important Facts

- The feature is described as relatively new.
- First run requires going through setup and login again.
- The usual `claude` flags (e.g. `-p`) can still be used.

## 7. Common Beginner Mistakes

- **Thinking the sandbox protects your project.** It protects your *computer*. Claude Code can still damage project files and Git history.
- **Being surprised by the login prompt.** It is expected, since the sandbox is a fresh environment.

## 8. Connections Between Concepts

This solves the main risk of `--dangerously-skip-permissions` from `lesson-14.md`. The built-in alternative without Docker is in `lesson-16.md`.

## 9. Practical Understanding

Use this when you want hands-off, uninterrupted work and already have Docker.

> **Transcript note:** several lines are cut off, including the end, where the flags that can be used are listed.
