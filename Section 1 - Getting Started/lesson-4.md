# 4: Claude Code Setup

## 1. Lesson Overview

How to install Claude Code and start it for the first time inside a project. After this lesson you should know what Claude Code is (a command-line tool), how to launch it, and why it asks whether you trust a folder.

## 2. Key Concepts

**Claude Code is a command-line tool**
- *Simple:* You use it by typing in a terminal, not by clicking buttons in a window.
- *Technical:* It is a CLI (Command Line Interface) program with no graphical interface of its own. It can connect to code editors, which gives you a partial graphical experience (see `lesson-7.md`).

**Claude Code works *on* your project**
- *Simple:* It is not just a chatbot that prints code. It acts inside your folder.
- *Technical:* It reads the files in the folder, writes code, and executes commands (for example, running automated tests).

**Trusting a folder**
- *Simple:* The first time you start it in a folder, it asks "do you trust this folder?"
- *Technical:* Because Claude Code reads files and runs commands there, a folder containing malicious code could be dangerous. Only run it in folders you know.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| CLI | A program you control by typing commands | This is Claude Code's main form |
| Terminal | The window where you type commands | Where Claude Code runs |
| Integrated terminal | The terminal built into an editor like VS Code | Lets you code and use Claude Code in one window |
| Trust prompt | The first-run warning about the folder | Your first safety checkpoint |

## 4. How Things Work

1. Install Claude Code using the commands from the official setup instructions (available for all operating systems).
2. Open your project folder in your editor (the instructor uses Visual Studio Code).
3. Open the terminal inside that project.
4. Type `claude` and press Enter.
5. On first run in that folder, confirm that you trust it.
6. You are now inside a Claude Code session.

## 5. Examples

```bash
cd my-project
claude
```

The instructor's demo project is a bare-bones Next.js project (a starting snapshot is attached to the course).

## 6. Important Facts

- Command to start: `claude`
- Works on Windows, macOS, and Linux.
- The trust warning appears the first time in each new folder.
- The install commands are **not** in the transcript; they are in the linked official setup page.

## 7. Common Beginner Mistakes

- **Thinking it is only a chat window.** It can run commands and change files, so treat it like a helper with real access to the project.
- **Running it in any random folder.** Start it only in folders whose content you trust.
- **Starting it in the wrong place.** Claude Code works on the folder you launched it from, so open the terminal in your project first.

## 9. Practical Understanding

Day to day, you open a project, open a terminal there, type `claude`, and start giving it tasks. Everything else in the course builds on this.

> **Transcript note:** the auto-generated transcript writes "Cloud Code" several times. This is a transcription error; the tool is **Claude Code**.
