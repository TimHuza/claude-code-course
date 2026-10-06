# 40: Using Screenshots For Prompting With Feedback

## 1. Lesson Overview

Claude Code can look at images, so you can show it a visual problem. After this you should know when a screenshot helps and when plain text is better.

## 2. Key Concepts

**Image vision**
- *Simple:* Claude Code can see pictures you paste in.
- *Technical:* The model accepts images as input. A pasted screenshot is attached to the prompt and sent along.

**Screenshot plus description**
- Paste the screenshot *and* describe the problem. The image supports the prompt; it does not replace it.

**Right tool for the problem**

| Problem | Best input |
|---|---|
| Something looks wrong (layout, styling, wrong content shown) | Screenshot + description |
| Error message | Copy and paste the raw text |

## 4. How Things Work

1. Take a screenshot of the problem.
2. Paste it into the Claude Code prompt.
3. Describe what is wrong and refer to the screenshot.
4. Send, then check the fix.

## 5. Examples

- The note editor showed raw JSON (the format in which the editor stores content) instead of formatted text → screenshot + explanation → fixed.
- The delete dialog was badly positioned and styled → a screenshot of the **whole page**, so the positioning problem is visible → fixed.

## 6. Important Facts

- The section's cheat sheet lists `Ctrl + V` / `Cmd + V` / `Alt + V` for inserting an image, depending on your system.
- Small hints steer the solution: the instructor asks for a confirmation dialog "using the native dialog element".

## 7. Common Beginner Mistakes

- **Screenshotting an error message.** Text is more precise; paste it as text.
- **Cropping too tightly.** For layout problems, show enough of the page to make the issue clear.
- **Sending only the image.** Always say what is wrong.

## 8. Connections Between Concepts

A screenshot is another kind of context (`lesson-21.md`). In `lesson-43.md` Claude Code takes its own screenshots through the browser.
