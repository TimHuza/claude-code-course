# 50: Dispatching Tasks From The Mobile App

## 1. Lesson Overview

Dispatch lets you send a task from your phone to the Claude desktop app on your computer. After this you should know what is required and why you must name the project folder.

## 2. Key Concepts

**Dispatch**
- *Simple:* Text a task from your phone; your computer at home does the work.
- *Technical:* The mobile app sends a task to the locally running desktop app. Originally a Cowork feature, it also works with Claude Code.

**Not tied to a project**
- *Simple:* The task arrives at "your computer", not at a particular project.
- *Technical:* Dispatch is a general desktop app feature. To have Claude Code work on a project, your message must say where the project folder is.

**Requirements**
- Computer on, desktop app running, dispatch enabled.
- Phone paired with the computer (one-time setup).

## 4. How Things Work

1. Enable dispatch in the desktop app.
2. Turn on **keep awake**, so the computer does not go to sleep.
3. Choose the code permissions.
4. Pair your phone in the mobile app's dispatch area.
5. Send a task that names the project.
6. The task appears in the desktop app as a new Claude Code session.
7. You get progress and a summary on your phone.

## 5. Examples

```
In the Claude Code project in my courses folder, change the primary color to an elegant pink.
```

## 6. Important Facts

- Consider bypass permissions for dispatched tasks, so they do not get stuck waiting for an approval nobody is there to give.
- **Computer use** can optionally be turned on, letting Claude control entire apps. The instructor leaves it off.
- Output is shown both on the desktop and in the mobile app.

## 7. Common Beginner Mistakes

- **Not naming the project.** Claude would have to guess the folder.
- **Letting the computer sleep.** Nothing runs then.
- **Confusing dispatch with cloud tasks.** Dispatch runs on *your* computer; cloud tasks (Section 2, `lesson-46.md`) run on Anthropic's servers.

## 8. Connections Between Concepts

Bypass permissions is the setting from `lesson-49.md`. The project-aware alternative is remote control (`lesson-51.md`).

> **Transcript note:** the instructor says "the Claude Code app" for the phone; the Claude mobile app is meant. He stresses that the described behavior is as of recording time.
