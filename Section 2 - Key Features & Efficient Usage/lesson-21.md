# 21: Making Sense of Prompt & Context Engineering

## 1. Lesson Overview

Defines what "prompt and context engineering" means. After this you should know the two ingredients of a good prompt.

## 2. Key Concepts

**Good input gives good results**
- *Simple:* The better you ask, the better the answer.
- *Technical:* Large language models can cope with poor prompts, but output quality typically follows input quality.

**A prompt has two parts**
1. **Specific instructions** that clearly describe the task or problem.
2. **Relevant context** and extra information.

**Unnecessary information hurts**
- Extra detail that does not matter can lead to *worse* output, not just a longer prompt.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Prompt engineering | Writing clear, specific instructions | Tells Claude Code *what* to do |
| Context engineering | Supplying the right background information | Gives Claude Code what it needs to do it well |
| Large language model (LLM) | The kind of AI behind Claude Code | It works only from the text it is given |

## 7. Common Beginner Mistakes

- **"More context is always better."** Only *relevant* context helps.
- **Thinking it is a special technique.** It simply means writing good prompts.

## 8. Connections Between Concepts

Context is limited (Section 1, `lesson-11.md`), which is one reason to avoid filling it with irrelevant material. The practical side follows in `lesson-22.md` and `lesson-23.md`.
