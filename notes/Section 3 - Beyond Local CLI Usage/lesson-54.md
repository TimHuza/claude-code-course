# 54: Scheduling Tasks With Claude Code

## 1. Lesson Overview

Claude Code can run a prompt automatically on a schedule. After this you should know the two places to set this up and the difference between them.

## 2. Key Concepts

**Scheduled task / routine**
- *Simple:* A task Claude Code repeats on its own, such as every weekday morning.
- *Technical:* A prompt sent to Claude Code on a schedule. Called **Routines** in the desktop app and reached with `/schedule` in the CLI.

**Where it can run**

| Set up in | Local tasks | Remote (cloud) tasks |
|---|---|---|
| Desktop app | Yes | Yes |
| CLI (`/schedule`) | No (at recording time) | Yes |

**Remote routines need GitHub**
- A cloud task works on a GitHub repository that the Claude Code cloud environment can access.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Routine | A scheduled task (desktop app name) | The feature's main name |
| Trigger | The CLI's word for a defined scheduled task | Same thing, different label |
| Schedule | When and how often it runs | Daily, weekdays, weekly, at a set time |

## 4. How Things Work

Desktop app:

1. Create a new routine, local or remote.
2. Give it a title and the prompt.
3. Assign a project folder, optionally a branch.
4. Choose permissions and model.
5. Set the schedule.

CLI:

1. Run `/schedule` (optionally followed by a short description).
2. Choose: view triggers, run one now, update, or create new.
3. Describe the task.
4. Provide the GitHub URL if the project has none linked.

## 5. Examples

```
/schedule
```

Task: "Analyze the recent changes and create a summary.md file."

## 6. Important Facts

- Bypass permissions can be given to a routine so it is not blocked waiting for approval.
- `/schedule` uses the AI model to build the schedule from your description.

## 7. Common Beginner Mistakes

- **Expecting `/schedule` to run tasks locally.** Use the desktop app for local routines.
- **Scheduling a remote task for a project not on GitHub.** The cloud cannot reach it.
- **Leaving a routine on default permissions.** It may stop at the first permission request.

## 8. Connections Between Concepts

Remote routines use the cloud environment from Section 2, `lesson-46.md`. Bypass permissions is covered in `lesson-49.md`.

> **Transcript note:** the instructor refers to "dispatching cloud tasks" earlier in the course; that is the cloud feature from Section 2, `lesson-46.md`, not the mobile dispatch feature from `lesson-50.md`.
