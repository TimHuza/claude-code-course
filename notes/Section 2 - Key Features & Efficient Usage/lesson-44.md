# 44: Providing Feedback via Automated Tests

## 1. Lesson Overview

Automated tests are a second way for Claude Code to verify its own work. After this you should know how to have Claude Code set up tests and what to watch out for.

## 2. Key Concepts

**Automated tests as feedback**
- *Simple:* Small programs that check whether your code does what it should.
- *Technical:* Unit, integration, and end-to-end tests all work. Claude Code runs them and fixes the errors it finds.

**Let the AI write them**
- Setting up a test library and writing tests is a task you can hand to Claude Code.

**The trap: tests that fit the code**
- AI tends to write tests that match the code already there, so they pass even if the code is wrong.
- Remedies: consider writing tests *before* the implementation, and review the tests like any other AI-written code.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Unit test | Tests one small piece of code | Fast, precise feedback |
| Integration test | Tests pieces working together | Catches connection problems |
| Mock | A stand-in for a real part (e.g. a database) | Makes code testable in isolation |
| Test runner | The tool that runs tests | Vitest in the demo |

## 4. How Things Work

1. Install a testing library (the instructor installs Vitest).
2. In plan mode, ask Claude Code to set it up and add tests.
3. Answer its questions (e.g. where the tests should live).
4. Accept the plan.
5. Claude Code writes the tests, runs them, and fixes failures.
6. Review the tests yourself.

## 5. Examples

Prompt (paraphrased):

```
I installed Vitest. I want unit tests. Set up the library appropriately and add
unit tests for all key features. Add mocks as needed and split complex functions
to simplify testing if needed.
```

Follow-up injected while it worked: use Vitest, not Bun's built-in test runner.

## 6. Important Facts

- You can inject a message into a running task (see `lesson-34.md`).
- You can ask for more tests later and name exactly which ones.

## 7. Common Beginner Mistakes

- **"All tests passed" means the code is right.** Only if the tests check the right things.
- **Not reviewing the tests.** Check what is tested and what is missing.
- **Leaving ambiguity.** Bun has its own test runner, so the instructor had to state which one to use.

## 8. Connections Between Concepts

Complements browser access (`lesson-43.md`): tests are cheaper and repeatable, the browser checks the real user experience. Both are required for the loop in `lesson-45.md`.
