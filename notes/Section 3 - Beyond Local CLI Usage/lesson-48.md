# 48: Advanced Claude Code Desktop Features

## 1. Lesson Overview

The desktop app's extra panels for understanding and steering Claude Code's work. After this you should know what the plan, tasks, preview, terminal, and diff views are for.

## 2. Key Concepts

**Expandable output**
- After a task, you can expand the output to see which files were edited and what exactly changed.

**Panels (top right)**

| Panel | What it shows |
|---|---|
| Plan | The plan Claude Code is working through (if one was made) |
| Tasks | The steps it is going through while working |
| Preview | Your running web app, inside the desktop app |
| Terminal | A built-in terminal for your own commands |
| Diff | All files changed and the exact changes |

**Preview**
- *Simple:* See your website next to the chat.
- *Technical:* On first use in a project, a setup task works out how the development server is started and saves that in a launch JSON file in the project's `.claude` folder. Afterwards the app can start the server for you.

**Point instead of describe**
- In the preview you can select page elements; in the diff you can comment on a line. Both are added to the chat as context.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Preview | Live view of your app | Check results without leaving the app |
| Diff viewer | Overview of all changes | Review what the agent did |
| Session logs | Output of the dev server | Shows errors |
| Element | A part of a web page (link, button, ...) | Can be selected as context |

## 4. How Things Work

Selecting an element:

1. Open Preview.
2. Select one or more elements on the page.
3. They appear in the chat box as context.
4. Write the instruction, e.g. "Make this link red".

Commenting in the diff:

1. Open the diff viewer.
2. Hover over a line and click the `+`.
3. Write the comment and add it; it appears in the chat as context.

## 6. Important Facts

- Preview can switch between dark and light mode (it signals the user's preference; the app must support it) and between mobile and desktop view.
- Selected elements and comments can be removed again from the chat box.
- The sidebar can be hidden for more room.
- Several sessions can run at once, across different projects.

## 7. Common Beginner Mistakes

- **Describing a location in words** ("in file X on line 10") when you could select or comment on it directly.
- **Expecting Plan and Tasks to always show content.** They are empty if no plan was made or the work is finished.
- **Expecting Preview to work immediately.** It needs the one-time setup.

## 8. Connections Between Concepts

The diff viewer is the desktop version of reviewing changes (Section 1, `lesson-7.md`). Selecting elements serves the same purpose as screenshots (Section 2, `lesson-40.md`): showing instead of describing.

> **Transcript note:** "Cloud Code" / "Cloud folder" are Claude Code and the `.claude` folder. The exact name of the launch file is not shown.
