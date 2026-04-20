# llm-wiki-bootstrap

An LLM Wiki on the LLM Wiki pattern. Built with Claude Code and browsed with Obsidian.

## Table of contents

- [1. What is an LLM Wiki?](#1-what-is-an-llm-wiki)
- [2. This repo](#2-this-repo)
  - [2.1 Browse the wiki](#21-browse-the-wiki)
  - [2.2 Query the wiki](#22-query-the-wiki)
- [3. Structure](#3-structure)
- [4. Getting started](#4-getting-started)
  - [4.1 Create a new wiki](#41-create-a-new-wiki)
    - [4.1.1 Claude command](#411-claude-command)
    - [4.1.2 Manual copy](#412-manual-copy)
  - [4.2 Ingest sources](#42-ingest-sources)
  - [4.3 Browse with Obsidian](#43-browse-with-obsidian)
  - [4.4 Query with Claude](#44-query-with-claude)
- [5. Operations](#5-operations)
- [6. Example prompts](#6-example-prompts)
- [7. Supported source formats](#7-supported-source-formats)

## 1. What is an LLM Wiki?

A knowledge base where the LLM does all the writing and maintenance — summarizing sources, creating interlinked pages, flagging contradictions, and keeping everything consistent. You curate the sources and ask the questions. The LLM handles the bookkeeping.

Based on [Andrej Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f).

## 2. This repo

This repo is itself an LLM Wiki — its topic is the LLM Wiki pattern. The `raw/` folder contains 15 ingested sources (Karpathy's original gist, Reddit discussions, Medium articles, tool documentation, and biographies), and the `wiki/` folder contains 16 interlinked pages built from those sources.

You can use it as a working example to explore before creating your own wiki.

### 2.1 Browse the wiki

Open this repo as an Obsidian vault to browse the wiki visually:

1. Open Obsidian
2. Select "Open folder as vault"
3. Choose this repo's directory
4. Navigate to `wiki/index.md` to see the table of contents
5. Use graph view to see how pages are connected

### 2.2 Query the wiki

Open Claude Code in this repo (via VS Code or terminal) and ask questions against the wiki:

- "What is the LLM Wiki pattern?"
- "What are the main criticisms of the pattern?"
- "How does RAG compare to the wiki approach?"
- "Who is Andrej Karpathy?"

Claude will read the wiki pages and synthesize answers with citations.

## 3. Structure

```
raw/              Source documents (immutable)
wiki/             LLM-maintained markdown pages
wiki/index.md     Table of contents
wiki/log.md       Append-only operation log
templates/        Reusable templates and starter kits
  base/           Starter kit for bootstrapping a new wiki
  pages/          Page templates (e.g. concept, entity, comparison)
  diagrams/       Diagram templates
  exports/        Export format templates
CLAUDE.md         Schema that governs LLM behavior
```

## 4. Getting started

### 4.1 Create a new wiki

There are two ways to create a new wiki:

#### 4.1.1 Claude command

From this repo, run the `/init-llm-wiki` command in Claude Code. It will ask you for:

1. The topic of the wiki
2. A name for the Obsidian vault
3. Where to save it

It copies the base template, configures CLAUDE.md with your topic, and creates the full folder structure.

#### 4.1.2 Manual copy

Copy `templates/base/` to a new directory:

```sh
cp -r templates/base/ ~/my-wiki
```

Edit `CLAUDE.md` and replace `[YOUR TOPIC HERE]` with your subject.

### 4.2 Ingest sources

Drop source documents into the `raw/` folder — articles, PDFs, CSVs, images, or any [supported format](#6-supported-source-formats). Then tell Claude to process them:

- "I added a new source to the raw folder. Read it and update the wiki."
- "Detect new files in raw and update the wiki."

Claude will read each source, discuss key takeaways with you, then create and update wiki pages with summaries, cross-references, and citations. A single source may touch 10–15 wiki pages.

### 4.3 Browse with Obsidian

Open the wiki directory as an Obsidian vault. Pages are interlinked with `[[wiki-links]]` and work natively with Obsidian's graph view, backlinks, and search.

### 4.4 Query with Claude

Use Claude Code to interact with your wiki — ingest sources, ask questions, and run lint checks. You can use it from:

- **VS Code** — via the Claude Code extension, directly alongside your wiki files
- **Terminal** — run `claude` from your wiki directory

Claude reads your `CLAUDE.md` schema automatically and knows how to operate the wiki. Just ask questions in plain language and it will search the wiki, synthesize answers, and cite its sources. See [section 6](#6-example-prompts) for example prompts.

## 5. Operations

- **Ingest**: Add a source to `raw/`, ask the LLM to process it. It creates/updates wiki pages, cross-references, index, and log.
- **Delete**: Remove a source from `raw/`, tell the LLM. It removes or flags unsupported claims and updates the wiki.
- **Update**: Replace a source in `raw/` with a new version, tell the LLM. It re-reads the source, updates affected pages, and flags new contradictions.
- **Query**: Ask questions. The LLM reads the wiki and synthesizes answers with citations. Good answers get filed back as new pages.
- **Lint**: Ask the LLM to audit the wiki for contradictions, orphan pages, missing concepts, and stale claims.

## 6. Example prompts

**Ingest**
- "I added a new source to the raw folder. Read it and update the wiki."
- "Detect new files in raw and update the wiki."
- "Ingest all new files."

**Delete**
- "I removed [filename] from raw. Update the wiki to remove claims from that source."
- "I deleted a source. Check which wiki pages cited it and clean them up."

**Update**
- "I updated [filename] in raw. Re-read it and update the wiki with any changes."
- "I replaced [filename] with a newer version. Update the wiki accordingly."

**Query**
- "What does the wiki say about [topic]?"
- "Summarize everything related to [concept]."
- "Compare [concept A] and [concept B] based on the wiki."
- "What sources discuss [topic]?"

**Lint**
- "Lint the wiki."
- "Are there any orphan pages?"
- "Check for contradictions between pages."
- "Which concepts are mentioned but don't have their own page?"

## 7. Supported source formats

Drop files into `raw/` for ingestion. Claude Code can read these natively:

- **Markdown** (`.md`) — the primary format
- **PDF** files
- **CSV** files
- **Plain text** files
- **Images** (PNG, JPG, etc.) — viewed separately, not inline with markdown

Use the **Obsidian Web Clipper** browser extension to convert any web article to markdown with one click.

Other formats need conversion before adding to `raw/`:

- **Apple Numbers** — export to CSV first (File > Export To > CSV)
- **Word docs, slides, etc.** — convert to markdown or PDF
