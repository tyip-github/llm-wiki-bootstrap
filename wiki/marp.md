# Marp

**Summary**: A markdown-based presentation ecosystem for creating slide decks. Used in the LLM Wiki workflow to generate presentations from wiki content.

**Sources**: Marp Markdown Presentation Ecosystem.md, Thread by @karpathy.md, llm-wiki.md

**Last updated**: 2026-04-14

---

## Overview

Marp (Markdown Presentation Ecosystem) converts markdown documents into slide decks. Pages are split by horizontal rules (`---`), and the format is based on CommonMark (source: Marp Markdown Presentation Ecosystem.md).

In the [[llm-wiki-pattern]], Karpathy uses Marp as one of the output formats — having the LLM render slideshows from wiki content, viewed in [[obsidian|Obsidian]] via the Marp plugin (source: Thread by @karpathy.md).

## Features

- **Based on CommonMark** with directives and extended syntax (image syntax, math typesetting, auto-scaling) (source: Marp Markdown Presentation Ecosystem.md)
- **3 built-in themes**: `default`, `gaia`, `uncover` (source: Marp Markdown Presentation Ecosystem.md)
- **Export formats**: HTML, PDF, and PowerPoint (powered by Chrome/Chromium) (source: Marp Markdown Presentation Ecosystem.md)
- **Custom theming** via plain CSS (source: Marp Markdown Presentation Ecosystem.md)
- **Pluggable architecture** built on the Marpit framework (source: Marp Markdown Presentation Ecosystem.md)

## Toolset

- **Marp for VS Code** — edit and preview slide markdown within VS Code (source: Marp Markdown Presentation Ecosystem.md)
- **Marp CLI** — command line conversion between formats (source: Marp Markdown Presentation Ecosystem.md)
- **Marp Core** — the converter engine used by all official tools (source: Marp Markdown Presentation Ecosystem.md)
- **Marpit framework** — the underlying skinny framework for HTML/CSS slide decks (source: Marp Markdown Presentation Ecosystem.md)

All tools are MIT-licensed and fully open-source (source: Marp Markdown Presentation Ecosystem.md).

## Related pages

- [[tooling]]
- [[obsidian]]
- [[karpathy-thread]]
- [[operations]]
