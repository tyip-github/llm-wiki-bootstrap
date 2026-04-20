# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

A knowledge base maintained by Claude Code, based on Andrej Karpathy's LLM Wiki pattern.
This repo is also an Obsidian vault — pages use `[[wiki-links]]` and are browsed via Obsidian's graph view.

## Purpose

This wiki is a structured, interlinked knowledge base for [YOUR TOPIC HERE].
Claude maintains the wiki. The human curates sources, asks questions, and guides the analysis.

## Folder structure

```
raw/                       -- source documents (immutable -- never modify these)
wiki/                      -- markdown pages maintained by Claude
wiki/index.md              -- table of contents for the entire wiki
wiki/log.md                -- append-only record of all operations
templates/                 -- reusable templates
  pages/                   -- page templates (e.g. page.md)
  diagrams/                -- diagram templates
  exports/                 -- export format templates
```

## Ingest workflow

When the user adds a new source to `raw/` and asks you to ingest it:

1. Read the full source document
2. Discuss key takeaways with the user before writing anything
3. Create a summary page in `wiki/` named after the source
4. Create or update concept pages for each major idea or entity
5. Add wiki-links ([[page-name]]) to connect related pages
6. Update `wiki/index.md` with new pages and one-line descriptions
7. Append an entry to `wiki/log.md` with the date, source name, and what changed

A single source may touch 10-15 wiki pages. That is normal.

## Delete a source

When the user removes a source from `raw/` and tells you:

1. Identify all wiki pages that cite the removed source
2. For claims that are only supported by the removed source, remove them or mark as needing verification
3. For claims supported by multiple sources, remove the deleted source from the citation but keep the claim
4. Remove or update the source summary page if one exists
5. Update `wiki/index.md` and append an entry to `wiki/log.md` noting the deletion

## Update a source

When the user replaces a source in `raw/` with an updated version:

1. Re-read the updated source
2. Compare against existing wiki content that cites this source
3. Update wiki pages with any changed information
4. Flag any new contradictions with other sources
5. Update `wiki/index.md` and append an entry to `wiki/log.md` noting the update

## Page format

Every wiki page should follow the template in `templates/pages/page.md`.

## Citation rules

- Every factual claim should reference its source file
- Use the format (source: filename.pdf) after the claim
- If two sources disagree, note the contradiction explicitly
- If a claim has no source, mark it as needing verification

## Question answering

When the user asks a question:

1. Read `wiki/index.md` first to find relevant pages
2. Read those pages and synthesize an answer
3. Cite specific wiki pages in your response
4. If the answer is not in the wiki, say so clearly
5. If the answer is valuable, offer to save it as a new wiki page

Good answers should be filed back into the wiki so they compound over time.

## Lint

When the user asks you to lint or audit the wiki:

- Check for contradictions between pages
- Find orphan pages (no inbound links from other pages)
- Identify concepts mentioned in pages that lack their own page
- Flag claims that may be outdated based on newer sources
- Check that all pages follow the page format above
- Report findings as a numbered list with suggested fixes

## Rules

- Never modify anything in the `raw/` folder
- Always update `wiki/index.md` and `wiki/log.md` after changes
- Keep page names lowercase with hyphens (e.g. `machine-learning.md`)
- Write in clear, plain language
- When uncertain about how to categorize something, ask the user

## Detect new files

When the user asks to detect or ingest new files:

1. List all files in `raw/` and compare against `wiki/log.md` to find unprocessed sources
2. Read each new source and follow the ingest workflow above

## Git workflow

- Always use `--no-ff` when merging branches into main
- Do not commit `.obsidian/` — it is in `.gitignore`
