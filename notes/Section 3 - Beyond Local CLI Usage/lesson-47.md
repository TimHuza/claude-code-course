# 47: Using the Claude Desktop App

## 1. Lesson Overview

A closer look at using Claude Code through the desktop app instead of the terminal. After this you should know how to start a session there and what the main controls do.

## 2. Key Concepts

**Three modes in one app**
- **Chat** – a general chatbot, nothing to do with coding.
- **Cowork** – like Claude Code but with a general work focus (e.g. creating slides).
- **Code** – Claude Code, the focus of the course.

**Sessions organized by project**
- *Simple:* All your conversations are listed, grouped by the project they belong to.
- *Technical:* The list includes both local sessions and cloud sessions, which you can start and manage from the app.

**Local or cloud**
- When starting a session you choose whether the task runs on your machine or in the cloud.

**Git worktree**
- *Simple:* A second copy of your project in another folder, so two tasks do not get in each other's way.
- *Technical:* A Git feature that creates a local copy of the repository for the checked-out branch in a different path. It does **not** create a new branch. If the option is ticked, Claude creates a worktree for every new session, and the work can be merged back later.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Session | One conversation / task run | The unit of work in the app |
| Worktree | A parallel local copy of a repository | Lets several sessions work at once |
| Branch | A separate line of changes in Git | You can pick which one a task runs in |
| Reasoning effort | How much thinking the model puts into a task | Selectable per task, next to the model |

## 4. How Things Work

1. Click **New session**.
2. Pick the project folder.
3. Choose local or cloud.
4. Optionally choose a branch or tick the worktree option.
5. Choose the permission mode, model, and reasoning effort.
6. Type the prompt and press Enter.

## 5. Examples

The task in the lesson: the edit-note page is narrower than the other pages, so the instructor asks Claude Code to make it full width, referencing the edit page file with `@`. It is sent in accept edits mode and done after changing two files.

## 6. Important Facts

In the prompt box you can:

- type `@` to reference a file
- click `+` to add files or images
- type `/` for slash commands (most of the CLI ones, including `/compact` and your skills)
- use voice dictation
- pick the permission mode: ask every time, accept edits, plan mode (bypass permissions must be enabled in settings first, see `lesson-49.md`)

## 7. Common Beginner Mistakes

- **Confusing a worktree with a branch.** A worktree is a copy of the files in another folder; no new branch is created.
- **Thinking the desktop app is a different Claude Code.** Same tool, same concepts, different interface.

## 8. Connections Between Concepts

This expands the brief preview in Section 1, `lesson-8.md`. Permission modes, `@` references, skills, and plan mode work as taught in Sections 1 and 2. Cloud sessions were introduced in Section 2, `lesson-46.md`.

> **Transcript note:** some sentences are cut off; the worktree explanation is given loosely ("kind of copies your repo"), so check Git's documentation for details.
