# 43: Creating Feedback Loops by Granting Browser Access

## 1. Lesson Overview

Giving Claude Code a browser lets it test its own work on a web app. After this you should understand what a feedback loop is and what browser access costs.

## 2. Key Concepts

**Feedback loop**
- *Simple:* Build, check, fix, check again, without you in between.
- *Technical:* When an agent can validate its work, it can detect issues, fix them, and re-test on its own.

**Browser access through Playwright**
- *Simple:* Claude Code opens a real browser and uses your app like a person would.
- *Technical:* Playwright was built for end-to-end testing of web apps and is now popular for giving coding agents browser access. Claude Code can navigate, fill in forms, click, open new tabs, take snapshots of the page, and inspect network activity.

**Cost**
- Browser access is token-intensive: tool descriptions, many tool calls, and viewing images all consume tokens.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Feedback loop | The agent checks and corrects its own work | Less manual testing for you |
| End-to-end testing | Testing an app the way a user uses it | Playwright's original purpose |
| Port | The number in an address like `localhost:3000` | Tells Claude Code where the app runs |

## 4. How Things Work

1. Start your development server.
2. Ask Claude Code to test the app with Playwright, and say where it is running.
3. Approve the Playwright tool requests.
4. Claude Code opens a browser and works through the features.
5. It reports problems, fixes them, and tests again.

## 5. Examples

```
Test the application you built using the Playwright plugin. Test all main features
step-by-step to make sure they work correctly. The application server is already
running on port 3001.
```

Sent with accept edits on, not in plan mode.

## 6. Important Facts

- On first use it asks permission for many separate Playwright actions (navigate, fill, click, snapshot). You can choose not to be asked again for each.
- Default port for the demo app is 3000; the instructor uses 3001.

## 7. Common Beginner Mistakes

- **Not saying where the app runs.** Give the port and state that the server is already running.
- **Using browser testing for everything.** It is powerful but expensive; use it deliberately.
- **Expecting no prompts.** The first run needs many approvals.

## 8. Connections Between Concepts

Uses the Playwright plugin from `lesson-42.md` and the image vision from `lesson-40.md` (now Claude Code takes the pictures itself). Automated tests are the other feedback method (`lesson-44.md`).
