# 52: Using Claude Code Channels (Telegram)

## 1. Lesson Overview

Channels let you send messages to Claude Code through a chat app of your choice. The lesson sets up Telegram. After this you should understand the idea and the setup steps.

## 2. Key Concepts

**Channels**
- *Simple:* Message Claude Code from a chat app, as if texting a colleague.
- *Technical:* A feature for pushing messages into a Claude Code session through a communication channel such as Slack, WhatsApp, or Telegram. You can build your own channel; some, like Telegram, are officially supported through plugins.

**Bot**
- *Simple:* An automated chat account that passes your messages along.
- *Technical:* You create a Telegram bot and get a bot token. The token connects the plugin to that bot.

**Pairing**
- *Simple:* Proving the bot is allowed to talk to *your* Claude Code.
- *Technical:* The bot gives you a pairing code, which you enter in Claude Code to authorize it for this installation.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Channel | A messaging route into Claude Code | Alternative to the Claude apps |
| Bot token | Secret key for your bot | Connects plugin and bot; keep it private |
| Pairing code | One-time code linking bot and installation | Stops others using your bot |

## 4. How Things Work

1. In Claude Code, install the plugin and choose the scope.
2. Reload plugins (or restart the session).
3. In Telegram, create a new bot with `/newbot`: give it a name and a username ending in `bot`. Copy the bot token.
4. In Claude Code, run the configure command with the token and approve the requests.
5. Reload plugins again.
6. In Telegram, message your bot (e.g. "hello") to receive a pairing code.
7. In Claude Code, run the pair command with that code.
8. Start Claude Code with the `--channels` flag. It now listens for messages.

## 5. Examples

```
/plugin install telegram@claude-plugins-official
/telegram:configure <bot-token>
/telegram:access pair <code>
```

```bash
claude --channels plugin:telegram@claude-plugins-official
```

Message sent from Telegram: "Create an HTML file with hello world inside". Claude Code does the work, the output appears in both places, and permission requests can be approved from Telegram.

## 6. Important Facts

- The Telegram plugin is distributed by Anthropic.
- The session must stay running and the computer must stay awake.
- A channel session can be started in any folder, so it can be used for non-coding work too.

## 7. Common Beginner Mistakes

- **Starting Claude Code normally afterwards.** Without `--channels` it does not listen.
- **Skipping the reload.** The plugin and its commands are not active until you reload or restart.
- **Sharing the bot token.** Whoever has it controls the bot.

## 8. Connections Between Concepts

A third way to reach Claude Code remotely, next to dispatch (`lesson-50.md`) and remote control (`lesson-51.md`), and the one that needs no Claude app. It is installed through the plugin system (Section 2, `lesson-42.md`).

> **Transcript notes:** the name of the Telegram account you create bots with is cut off; it is Telegram's official **BotFather** (additional knowledge). Command spellings are reconstructed from speech (the pair command is transcribed as "/telegram:accesspair"); Telegram shows you the exact command to run.
