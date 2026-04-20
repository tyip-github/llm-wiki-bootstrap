# Tooling

**Summary**: Overview of the tool ecosystem for the LLM Wiki pattern, with links to dedicated pages for key tools.

**Sources**: llm-wiki.md, Thread by @karpathy.md

**Last updated**: 2026-04-14

---

## Overview

The [[llm-wiki-pattern]] relies on a small set of tools. The wiki is just a git repo of markdown files — version history, branching, and collaboration come for free (source: llm-wiki.md).

## Core tools

- **[[obsidian|Obsidian]]** — the primary interface ("IDE") for browsing the wiki. Features graph view, Web Clipper, Dataview, and Canvas. See dedicated page for full detail.
- **[[qmd|Qmd]]** — local search engine with BM25, vector search, and LLM re-ranking. Becomes useful when the wiki outgrows index-based navigation (~100+ pages). See dedicated page.
- **[[marp|Marp]]** — markdown-based slide deck format for generating presentations from wiki content. See dedicated page.
- **Git** — version control for the wiki. Commit after every ingest; easier to roll back than to fix (source: llm-wiki.md).

## LLM agents

The LLM agent is the engine that builds and maintains the wiki. Common options:

- **Claude Code** — Anthropic's terminal-based coding agent with direct filesystem access. Most commonly recommended for this workflow (source: Thread by @karpathy.md).
- **OpenAI Codex**, **Cursor**, and other tools that can read and write local files also work (source: Thread by @karpathy.md).

## See also

- [[setup-guides]] — step-by-step instructions for setting up the full tool stack

## Related pages

- [[llm-wiki-pattern]]
- [[architecture]]
- [[operations]]
- [[obsidian]]
- [[qmd]]
- [[marp]]
- [[setup-guides]]
