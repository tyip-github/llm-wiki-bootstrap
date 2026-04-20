# LLM Wiki (Source Summary)

**Summary**: Summary of Andrej Karpathy's original gist describing the LLM Wiki pattern — a method for building personal knowledge bases using LLMs.

**Sources**: llm-wiki.md

**Last updated**: 2026-04-14

---

## Overview

This gist by Andrej Karpathy introduces the [[llm-wiki-pattern]] — a design pattern where an LLM incrementally builds and maintains a persistent wiki from raw source documents (source: llm-wiki.md). The document is intentionally abstract, describing the idea rather than a specific implementation.

## Key points

- The pattern contrasts with [[rag-vs-wiki|RAG-based approaches]]: instead of re-deriving answers from raw documents on every query, the LLM compiles knowledge once into a structured wiki and keeps it current (source: llm-wiki.md).
- The [[architecture]] has three layers: raw sources (immutable), the wiki (LLM-maintained markdown), and the schema (a config file like CLAUDE.md) (source: llm-wiki.md).
- Three core [[operations]]: **ingest** (process new sources into wiki pages), **query** (answer questions from the wiki), and **lint** (health-check the wiki) (source: llm-wiki.md).
- The human's role is to curate sources, direct analysis, and ask good questions. The LLM handles all the bookkeeping — summarizing, cross-referencing, filing, and maintenance (source: llm-wiki.md).
- Good answers should be filed back into the wiki so explorations compound over time (source: llm-wiki.md).
- The pattern is related to Vannevar Bush's [[memex]] (1945) — a personal knowledge store with associative trails (source: llm-wiki.md).

## Use cases

The document suggests several domains where the pattern applies (source: llm-wiki.md):

- **Personal**: goals, health, self-improvement journals
- **Research**: deep-diving a topic over weeks/months with papers and articles
- **Reading a book**: building companion wikis with characters, themes, plot threads
- **Business/team**: internal wikis fed by Slack, meeting transcripts, project docs
- **Other**: competitive analysis, due diligence, trip planning, course notes, hobby deep-dives

## Practical advice

The gist recommends several [[tooling|tools and tips]] for working with the pattern, including Obsidian Web Clipper, local image downloads, graph view, Marp for slide decks, and Dataview for frontmatter queries (source: llm-wiki.md).

## Related pages

- [[llm-wiki-pattern]]
- [[rag-vs-wiki]]
- [[architecture]]
- [[operations]]
- [[memex]]
- [[tooling]]
- [[community-reception]]
- [[criticisms]]
