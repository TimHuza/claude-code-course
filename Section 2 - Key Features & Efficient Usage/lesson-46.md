# 46: Using Claude Code Web (Cloud)

## 1. Lesson Overview

Tasks can run on Anthropic's servers instead of your computer. After this you should know the requirements, the ways to start a cloud task, and how the result comes back.

## 2. Key Concepts

**Claude Code in the cloud**
- *Simple:* Hand over a task, close your laptop, and it keeps working.
- *Technical:* The cloud session checks out your GitHub repository and branch, works on the code, and can run tests there. The result arrives on a **new branch** with a **pull request**, not pushed to your main branch.

**Requirements (at recording time)**
- A Pro, Max, Team, or Enterprise subscription.
- Code in a GitHub repository.
- Your Claude account connected to GitHub, with access granted per repository.
- A cloud environment.

**Network access of the environment**

| Setting | Meaning |
|---|---|
| Trusted | Limited internet access (the instructor's choice) |
| Full | Maximum flexibility, e.g. if tests call external services, but full exposure to internet threats |

**Mixing local and cloud**
- Plan locally (planning needs your answers), then hand the implementation to the cloud.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Repository | A project stored in Git/GitHub | The cloud works on this copy |
| Branch | A separate line of changes | Keeps cloud work apart from main |
| Pull request (PR) | A proposal to merge a branch | Where you review the result |
| Cloud environment | The remote machine setup for tasks | Must exist before starting |

## 4. How Things Work

1. Push your project to GitHub.
2. Go to `claude.ai/code` and connect GitHub.
3. Authorize the repository.
4. Create a cloud environment and pick the network access.
5. Start a task (web or local, see below).
6. Claude Code works remotely on a new branch.
7. Review the changes and merge the pull request if you are happy.

## 5. Examples

Three ways to start a cloud task:

| Where | How |
|---|---|
| Web | Pick repository, branch, environment, and model; type the task |
| Local session | Put `&` in front of the prompt |
| Terminal | `claude --remote "your prompt"` |

```
& change the main color from blue to an elegant purple
```

```bash
claude --remote "change the main color from blue to an elegant purple"
```

## 6. Important Facts

- Several cloud tasks can run in parallel.
- Images can be attached in the web interface.
- A link to the remote session is shown; you can enable notifications.
- The feature was in beta / research preview and somewhat buggy when started from the local client; starting from the web worked reliably for the instructor.

## 7. Common Beginner Mistakes

- **Expecting it to see local files.** It works on what is pushed to GitHub.
- **Expecting changes on main.** They arrive as a branch and pull request for review.
- **Choosing full internet access by default.** Only when the task needs it.
- **Running plan mode remotely.** Do the planning locally.

## 8. Connections Between Concepts

A third way of working, next to interactive sessions and the Ralph loop (`lesson-45.md`). It relies on Git (Section 1, `lesson-17.md`) and plan mode (`lesson-27.md`).

> **Transcript notes:** the command for choosing the remote environment is transcribed as "/remoteenv"; the exact spelling may differ (possibly `/remote-env`). The `&` handoff failed for the instructor with a false "not a Git repository" error, and he used `claude --remote -c` as a workaround. Behavior may have changed since.
