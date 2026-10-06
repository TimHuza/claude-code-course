# 41: Understanding & Using Hooks

## 1. Lesson Overview

Hooks run something automatically whenever Claude Code does a certain thing. The example formats code after every file edit. After this you should understand the parts of a hook.

## 2. Key Concepts

**Hook**
- *Simple:* "Whenever X happens, automatically do Y."
- *Technical:* Claude Code emits events. A hook reacts to an event by running code of your choice.

**Parts of a hook**

| Part | Meaning | In the example |
|---|---|---|
| Event | When to react | After a tool was used |
| Matcher | Which tool(s) it applies to | Edit or Write |
| Type | What kind of action | `command` |
| Command | What to run | The format script |

**Events**
- *Pre tool use* – before Claude Code uses a tool (web search, reading, editing a file, ...).
- *Post tool use* – after a tool was used.
- More are listed in the official docs.

**Hook types**
- `command` – runs a Bash command in a new terminal session.
- `prompt` – injects a prompt into the conversation.
- `agent` – also exists; `command` and `prompt` are the usual ones.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Event | Something Claude Code does that you can react to | The trigger |
| Matcher | Filter choosing which tools trigger the hook | Avoids running on everything |
| Formatter | A tool that restyles code consistently | The example's purpose |
| `CLAUDE_PROJECT_DIR` | Variable holding the current project folder | Lets the command find your project |

## 4. How Things Work

1. Claude Code edits or writes a file.
2. The post tool use event fires.
3. The matcher confirms the tool was Edit or Write.
4. The command runs: go to the project folder, run the formatter.
5. Claude Code continues.

## 5. Examples

Reconstructed from the instructor's description (check the official docs for exact spelling):

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "cd \"$CLAUDE_PROJECT_DIR\" && bun run format 2>/dev/null || true"
          }
        ]
      }
    ]
  }
}
```

- `|` in the matcher means "or".
- `2>/dev/null` hides error output; `|| true` makes the command always count as successful, so a formatting failure does not stop Claude Code.

## 6. Important Facts

- Hooks go in a settings file under a `hooks` entry: the project's local settings file (not in version control) or the global one.
- `/hooks` – view and set up hooks interactively.
- Start a new session after adding a hook so it is loaded.
- Event names must be written exactly as in the documentation.

## 7. Common Beginner Mistakes

- **Thinking a hook is an instruction to the AI.** A command hook is run by Claude Code itself, every time, independent of what the model decides.
- **Letting a failing hook block work.** Add a safe fallback for non-critical tasks.
- **Hard-coding the folder path.** Use the provided variable.

## 8. Connections Between Concepts

Hooks live in the settings files from Section 1, `lesson-9.md`. An instruction in `CLAUDE.md` (`lesson-25.md`) is something the model *should* follow; a hook *will* run.

## 9. Practical Understanding

Use hooks for things that must always happen after an action: formatting, linting, similar checks.

> **Transcript notes:** the transcript spells the events "pre-tool-use" / "post-tool-use" and the formatter "OxFormat"; exact names are not visible. The rest of the lesson builds the public-sharing feature of the demo app, which confirmed the hook worked (new files had single quotes).
