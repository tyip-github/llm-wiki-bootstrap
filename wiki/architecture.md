# Architecture

**Summary**: The LLM Wiki pattern uses a three-layer architecture: raw sources, the wiki, and the schema.

**Sources**: llm-wiki.md

**Last updated**: 2026-04-14

---

## Three layers

### Raw sources

A curated collection of source documents — articles, papers, images, data files. These are **immutable**: the LLM reads from them but never modifies them. This is the source of truth (source: llm-wiki.md).

### The wiki

A directory of LLM-generated markdown files. Summaries, entity pages, concept pages, comparisons, an overview, a synthesis. The LLM owns this layer entirely — it creates pages, updates them when new sources arrive, maintains cross-references, and keeps everything consistent. The human reads it; the LLM writes it (source: llm-wiki.md).

### The schema

A document (e.g. CLAUDE.md for Claude Code, AGENTS.md for Codex) that tells the LLM how the wiki is structured, what conventions to follow, and what workflows to use when ingesting sources, answering questions, or maintaining the wiki. This is the key configuration file — it makes the LLM a disciplined wiki maintainer rather than a generic chatbot. The human and LLM co-evolve this over time (source: llm-wiki.md).

## Special files

Two special files help navigate the wiki as it grows (source: llm-wiki.md):

- **index.md** — content-oriented. A catalog of every page with links, one-line summaries, and optional metadata. Organized by category. The LLM reads it first when answering queries (source: llm-wiki.md).
- **log.md** — chronological. An append-only record of [[operations]] — ingests, queries, lint passes. Using a consistent prefix format (e.g. `## [2026-04-02] ingest | Article Title`) makes it parseable with simple unix tools (source: llm-wiki.md).

## Infrastructure

The wiki is just a git repo of markdown files — version history, branching, and collaboration come for free (source: llm-wiki.md). At small scale, the index file is sufficient for navigation. As the wiki grows, tools like [[tooling|qmd]] can provide proper search (source: llm-wiki.md).

## Related pages

- [[llm-wiki-pattern]]
- [[operations]]
- [[tooling]]
- [[criticisms]]
