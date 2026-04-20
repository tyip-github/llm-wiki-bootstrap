# Setup Guides

**Summary**: Consolidated practical guidance for setting up an LLM Wiki, drawn from multiple how-to sources covering Obsidian setup, Claude Code integration, and best practices.

**Sources**: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md, LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md, Karpathy's LLM Wiki - Full Beginner Setup Guide.md

**Last updated**: 2026-04-14

---

## Overview

Multiple guides have been published explaining how to set up an LLM Wiki from scratch. The core steps are consistent across sources: install [[obsidian|Obsidian]], create a folder structure, write a schema file (CLAUDE.md), and start ingesting sources.

## Step-by-step setup

### 1. Install Obsidian and create a vault

Download Obsidian from obsidian.md. Create a new vault — this is just a folder. Place it somewhere memorable like `~/wiki` or `~/Documents/llm-wiki` (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md, Karpathy's LLM Wiki - Full Beginner Setup Guide.md).

### 2. Create the folder structure

```
raw/          -- source documents (immutable)
wiki/         -- AI-maintained markdown pages
templates/    -- optional page templates
```

(source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)

### 3. Create the schema file (CLAUDE.md)

Place a `CLAUDE.md` in the vault root. This tells the LLM how to structure the wiki, handle new sources, format pages, and answer questions. Key sections: purpose, folder structure, ingest workflow, page format, citation rules, and question answering behavior (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md).

The purpose line is the main thing to customize — everything else works as a solid starting point and evolves as the wiki grows (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md).

### 4. Install a coding agent

Claude Code is the most commonly recommended agent. Install via `npm install -g @anthropic-ai/claude-code`, authenticate, then navigate to your vault folder and run `claude` (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md).

Other options: OpenAI Codex, Cursor, or other tools that can read and write local files (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md).

### 5. Install Web Clipper

Add the Obsidian Web Clipper browser extension to convert web articles to markdown with one click. After clipping, download images locally with Ctrl+Shift+D (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md).

### 6. Ingest your first source

Drop a document into `raw/` and tell the agent: "I just added a new source to the raw folder. Please read it and update the wiki." The LLM will read it, create wiki pages, update the index, and log the changes (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md).

Sources can be markdown, PDF, or text files — the agent handles all formats (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md).

## Best practices

- **Write summaries**: A one-line summary at the top of each note helps the LLM quickly judge relevance (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md)
- **Use consistent terminology**: Pick one term for each concept. Add alias lines if a concept has multiple names (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md)
- **Link notes**: Obsidian's `[[wiki-links]]` create a graph the LLM can traverse for richer reasoning (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md)
- **Keep notes focused**: Ten focused 1,000-word notes are more queryable than one 10,000-word catch-all (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md)
- **Use an inbox pattern**: Dump rough notes into `/inbox`, then periodically ask the LLM to triage and file them (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md)
- **Classify before extracting**: Different document types (research papers, tweets, meeting transcripts) need different extraction approaches (source: LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md)
- **Commit after every ingest**: Use git to track changes; easier to roll back than to fix (source: LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md)

## Scaling with search

At small scale, the index file is sufficient. When the wiki exceeds ~100 pages, the index may not fit in one context window. [[qmd|Qmd]] provides local hybrid search (BM25 + vector + LLM re-ranking) as a solution (source: LLM Wiki Revolution How Andrej Karpathy's Idea is Changing AI.md).

For semantic search at larger scale, LlamaIndex can be used to build a retrieval layer over the wiki (source: What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code.md).

## Use cases

- **Students/researchers**: Build a wiki as you read papers; end up with structured knowledge, not highlighted PDFs (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)
- **Teachers**: Feed in curriculum documents and professional development materials (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)
- **Businesses**: Ingest meeting notes, customer calls, project docs — new team members browse the wiki instead of digging through Slack (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)
- **Curious readers**: Track what you learn from books, podcasts, articles — a personal encyclopedia (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)

## Limitations noted

- Works best at personal scale; tens of thousands of pages need more infrastructure (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)
- Garbage in, garbage out — curation matters (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)
- Requires a coding agent (Obsidian alone doesn't do this) (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)
- The AI can miscategorize or misconnect — use [[operations|lint]] to catch errors (source: Karpathy's LLM Wiki - Full Beginner Setup Guide.md)

## Related pages

- [[llm-wiki-pattern]]
- [[architecture]]
- [[operations]]
- [[obsidian]]
- [[qmd]]
- [[tooling]]
- [[criticisms]]
