# Qmd

**Summary**: A local search engine for markdown files combining BM25, vector search, and LLM re-ranking. Designed for LLM Wiki workflows with CLI, SDK, and MCP server support.

**Sources**: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md, LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md, llm-wiki.md

**Last updated**: 2026-04-14

---

## Overview

Qmd (Query Markup Documents) is an on-device search engine created by Tobi Lütke (CEO of Shopify) for indexing markdown notes, meeting transcripts, documentation, and knowledge bases. It combines three search approaches — all running locally via node-llama-cpp with GGUF models, requiring no API connections (source: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md).

In the [[llm-wiki-pattern]], qmd becomes useful when the wiki outgrows what a simple index.md can handle in one context window (~100+ pages) (source: LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md).

## Search modes

1. **`qmd search`** — Fast BM25 keyword search (source: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md)
2. **`qmd vsearch`** — Semantic vector search, finds related concepts even with different wording (source: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md)
3. **`qmd query`** — Hybrid search with LLM re-ranking for highest quality results, combining BM25 and vector results via Reciprocal Rank Fusion (RRF) (source: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md)

## Collections and contexts

Qmd organizes content into **collections** (directories of files) and supports **contexts** — descriptive metadata attached to collections that help LLMs make better contextual choices when selecting documents (source: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md).

## MCP server

Qmd exposes an MCP (Model Context Protocol) server for tight integration with LLM agents. Tools exposed: `query`, `get`, `multi_get`, and `status`. Supports both stdio (subprocess) and HTTP transport modes. The HTTP mode keeps LLM models loaded in VRAM across requests for performance (source: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md).

## Installation

```bash
npm install -g @tobilu/qmd
qmd collection add ./wiki --name my-research
qmd embed  # generate embeddings for semantic search
```

(source: tobiqmd mini cli search engine for your docs, knowledge bases, meeting notes, whatever. Tracking current sota approaches while being all local.md)

## Related pages

- [[tooling]]
- [[obsidian]]
- [[architecture]]
- [[operations]]
