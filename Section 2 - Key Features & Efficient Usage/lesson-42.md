# 42: Installing & Using Plugins

## 1. Lesson Overview

Plugins let you install ready-made bundles of Claude Code features instead of building everything yourself. After this you should know how to browse, install, and scope a plugin.

## 2. Key Concepts

**Plugin**
- *Simple:* A package of extras you install in one step.
- *Technical:* A bundle of things like skills, commands, and MCP servers that can be shared with others easily.

**Marketplace**
- *Simple:* A catalogue of plugins.
- *Technical:* The official marketplace, maintained by Anthropic, is included by default. You can add others, such as a company-internal one. Despite the name, plugins are free.

**Install scope**

| Scope | Available in | Shared via Git? |
|---|---|---|
| User | All your projects | No |
| Project | This project | Yes |
| Local | This project, only you | No |

These map to the three settings files from Section 1, `lesson-9.md`.

## 3. Important Terminology

| Term | Meaning | Why it matters |
|---|---|---|
| Plugin | Installable bundle of features | Saves setup time |
| Marketplace | Source of plugins | Where you discover them |
| LSP | Language Server Protocol; gives tools deeper understanding of code | Helps Claude Code detect errors |
| Playwright | A browser automation tool | Gives Claude Code browser access |

## 4. How Things Work

1. Run `/plugin`.
2. Move between the tabs (Discover, Installed, Marketplaces) with the arrow keys.
3. Press `Space` to select a plugin, `Enter` for details.
4. Choose the scope and install.
5. The matching `settings.json` is updated.

## 5. Examples

- **TypeScript LSP** – helps Claude Code detect TypeScript errors. Installed with *project* scope, because not all of the instructor's projects use TypeScript.
- **Playwright** – browser access. Installed with *user* scope (global).

## 6. Important Facts

- `/plugin` – open the plugin manager.
- MCP servers count as plugins: Context7 appears under Installed although it was added differently (`lesson-29.md`).
- The Playwright plugin is essentially an MCP server installed as a plugin.
- You can also build your own plugins (see the official docs).

## 7. Common Beginner Mistakes

- **Installing everything globally.** Use project scope for technology-specific plugins.
- **Thinking plugins are a new kind of feature.** They package features you already know.
- **Thinking "marketplace" means paid.**

## 8. Connections Between Concepts

Plugins bundle skills (`lesson-34.md`), commands (`lesson-39.md`), and MCP servers (`lesson-29.md`). Playwright is used in `lesson-43.md`.
