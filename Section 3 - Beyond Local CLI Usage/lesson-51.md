# 51: Using Claude Code Remote Control

## 1. Lesson Overview

Remote control lets you operate a Claude Code session running on your computer from another device. After this you should know how to start it and how it differs from dispatch.

## 2. Key Concepts

**Remote control**
- *Simple:* Leave your desk and keep the same conversation going from your phone.
- *Technical:* You start it on the machine where the work should run. Other devices (mobile app or a web link) connect and send prompts. Everything executes on your computer, not on the phone and not in the cloud.

**Remote control vs dispatch**

| | Dispatch (`lesson-50.md`) | Remote control |
|---|---|---|
| Needs | Desktop app running | A remote control session running in the CLI |
| Attached to a project | No, you describe the folder | Yes, the folder it was started in |
| Continue an existing session | No | Yes |
| Started from | The other device | The computer itself |

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Remote control session | A local session that accepts prompts from other devices | The thing your phone connects to |
| Same dir | Work in the current directory (the default) | One of two start modes |
| Worktree mode | Work in a Git worktree copy | For parallel agents (see `lesson-47.md`) |

## 4. How Things Work

1. In your project, start remote control (activate it the first time).
2. Choose the mode: same directory or worktree.
3. Open the shown link, or open the mobile app, start a new session, and select the remote control session.
4. Send prompts from that device.
5. Watch the progress there while the work happens on your computer.

## 5. Examples

Starting it:

```bash
claude remote-control
```

or, inside a running session, the remote control slash command.

Prompt sent from the phone (paraphrased): "My buttons are still blue although I tried to change them to purple. Investigate and fix."

## 6. Important Facts

- CLI-only at recording time: the desktop app's "add remote control" button just shows the CLI command.
- The session must keep running and the computer must not sleep. If either stops, the remote session stops.
- It has access to everything set up in the project, exactly like normal CLI use.
- Starting it from inside an ongoing conversation lets you continue that conversation elsewhere.

## 7. Common Beginner Mistakes

- **Thinking the work runs on the phone or in the cloud.** It runs on your computer.
- **Closing the terminal.** That ends the session.
- **Choosing dispatch when the project matters.** Remote control already knows the project.

## 8. Connections Between Concepts

It pairs with resuming sessions (Section 1, `lesson-13.md`): resume an old session, then hand it to another device.

> **Transcript note:** the commands are transcribed as "/remotectrol" and "Claude Remote Control". The exact spelling is not visible; it is most likely `/remote-control` and `claude remote-control`, so verify in your version.
