# Operations

**Summary**: The three core operations of the LLM Wiki pattern: ingest (process new sources), query (answer questions), and lint (health-check the wiki).

**Sources**: llm-wiki.md, Karpathy's LLM Wiki and why it feels kind of a game changer.md

**Last updated**: 2026-04-14

---

## Ingest

The user drops a new source into the raw collection and tells the LLM to process it. A typical flow (source: llm-wiki.md):

1. The LLM reads the source
2. Discusses key takeaways with the user
3. Writes a summary page in the wiki
4. Updates the index
5. Updates relevant entity and concept pages across the wiki
6. Appends an entry to the log

A single source might touch 10–15 wiki pages. The author prefers to ingest sources one at a time and stay involved — reading summaries, checking updates, guiding emphasis. But batch-ingesting with less supervision is also possible (source: llm-wiki.md).

## Query

The user asks questions against the wiki. The LLM searches for relevant pages, reads them, and synthesizes an answer with citations (source: llm-wiki.md).

Answers can take different forms: a markdown page, a comparison table, a slide deck (Marp), a chart (matplotlib), a canvas (source: llm-wiki.md).

**Key insight**: Good answers should be filed back into the wiki as new pages. A comparison, an analysis, a connection discovered — these are valuable and should not disappear into chat history. This way explorations compound in the knowledge base just like ingested sources do (source: llm-wiki.md).

## Lint

Periodic health-checks of the wiki. Things to look for (source: llm-wiki.md):

- Contradictions between pages
- Stale claims superseded by newer sources
- Orphan pages with no inbound links
- Important concepts mentioned but lacking their own page
- Missing cross-references
- Data gaps that could be filled with a web search

The LLM is good at suggesting new questions to investigate and new sources to look for. Linting keeps the wiki healthy as it grows (source: llm-wiki.md).

### Staleness and silent drift

A key failure mode: the LLM cannot know when a fact has changed, so it may return outdated context with full confidence. Silent drift is the real risk. Mitigation requires explicit freshness metadata alongside the wiki content — source version, ingestion timestamp, and explicit TTLs (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, ultrathink-art). See also [[community-reception]].

## Practical tips from practitioners

Community members shared refinements to the core operations (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, Ghiren):

1. **Dates and timestamps on logs** — ensures chronological order; critical when switching between different LLM agents, where append-only instructions can be lost
2. **Git hygiene** — commit after every log-worthy change; easier to ask the agent to roll back than to fix mistakes manually
3. **Hierarchical index** — for very large wikis, a single index.md may not scale; category-based indices work well
4. **MCP tool discovery** — index.md could be adapted so an agent can index a large array of MCP tools without filling context with tool descriptions

## Related pages

- [[llm-wiki-pattern]]
- [[architecture]]
- [[tooling]]
- [[community-reception]]
