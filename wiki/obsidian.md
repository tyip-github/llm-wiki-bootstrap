# Obsidian

**Summary**: A free, local-first markdown editor used as the primary interface for browsing and viewing LLM Wiki content. Features graph view, plugins, and the Web Clipper extension.

**Sources**: Sharpen your thinking.md, Thread by @karpathy.md, llm-wiki.md, LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md, What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md, Karpathy's LLM Wiki - Full Beginner Setup Guide.md

**Last updated**: 2026-04-14

---

## Overview

Obsidian is a free markdown knowledge management application that stores notes privately on the user's device using open file formats (source: Sharpen your thinking.md). In the [[llm-wiki-pattern]], it serves as the "IDE" — the viewing interface for the wiki — while the LLM is the "programmer" and the wiki is the "codebase" (source: Thread by @karpathy.md).

A "vault" in Obsidian is simply a folder on disk. Everything in it is plain markdown (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md).

## Key features for LLM Wiki

### Graph view

Visualizes relationships between notes as nodes and edges. Wiki-links become edges connecting pages. Hub pages appear as larger nodes; orphan pages appear as isolated nodes. This provides an immediate visual representation of knowledge density and gaps (source: LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md).

### Web Clipper

A browser extension (Chrome, Firefox, Safari, Edge, Arc, Brave) that converts web articles to clean markdown with YAML frontmatter in one click, saving directly to the raw folder (source: LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md). Karpathy uses this as the primary way to get sources into the raw collection (source: Thread by @karpathy.md).

### Image handling

In Settings, set "Attachment folder path" to a fixed directory (e.g. `raw/assets/`), then bind a hotkey (Ctrl+Shift+D) for "Download attachments for current file." After clipping, the hotkey downloads all images locally so the LLM can reference them directly (source: llm-wiki.md).

Note: LLMs cannot natively read markdown with inline images in one pass. The workaround is to have the LLM read the text first, then view referenced images separately (source: llm-wiki.md).

### Dataview plugin

Runs SQL-like queries over page frontmatter. If pages have YAML frontmatter (tags, dates, confidence levels), Dataview can generate dynamic tables — e.g. listing all low-confidence pages that need review, or pages not updated in 14 days (source: LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md).

### Canvas

An infinite space for research, brainstorming, diagramming, and laying out ideas (source: Sharpen your thinking.md).

### Sync and Publish

Obsidian offers optional paid features: **Sync** for end-to-end encrypted cross-device access with version history, and **Publish** for turning notes into an online wiki or digital garden (source: Sharpen your thinking.md).

## Core principles

- **Privacy**: Notes stored locally on device, accessible offline (source: Sharpen your thinking.md)
- **Flexibility**: Thousands of plugins and themes via open API (source: Sharpen your thinking.md)
- **Portability**: Open file formats (plain `.md` files), no lock-in (source: Sharpen your thinking.md)

## Related pages

- [[llm-wiki-pattern]]
- [[tooling]]
- [[qmd]]
- [[marp]]
- [[karpathy-thread]]
- [[setup-guides]]
