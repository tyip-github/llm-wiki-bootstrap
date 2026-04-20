# LLM Wiki Pattern

**Summary**: A design pattern where an LLM incrementally builds and maintains a persistent, interlinked wiki from raw sources — creating a compounding knowledge artifact rather than re-deriving answers on each query.

**Sources**: llm-wiki.md, Karpathy's LLM Wiki and why it feels kind of a game changer.md, Andrej Karpathy's LLM Wiki Bye Bye RAG.md, Andrej Karpathy 1.md, Thread by @karpathy.md

**Last updated**: 2026-04-14

---

## Core idea

Most people's experience with LLMs and documents looks like RAG: upload files, retrieve relevant chunks at query time, generate an answer. This works, but the LLM rediscovers knowledge from scratch on every question. There is no accumulation (source: llm-wiki.md).

The LLM Wiki pattern is different. Instead of retrieving from raw documents at query time, the LLM **incrementally builds and maintains a persistent wiki** — a structured, interlinked collection of markdown files that sits between the user and the raw sources (source: llm-wiki.md).

When a new source is added, the LLM reads it, extracts key information, and integrates it into the existing wiki — updating entity pages, revising topic summaries, noting contradictions, and strengthening or challenging the evolving synthesis (source: llm-wiki.md).

## Concrete example: EV research

To illustrate, consider researching electric vehicles with three sources: a Tesla annual report, a battery technology deep-dive, and an EV market trends blog. In a RAG system, these remain three isolated documents. In an LLM Wiki, the LLM creates structured pages for "Tesla", "Battery Technology", and "EV Market Trends" and **links them**: the Tesla page references battery technology, the battery page mentions cost reductions, and the market trends page connects both to adoption rates. When asked "Who will dominate EV batteries?", the LLM navigates pre-built, interlinked pages rather than re-searching raw PDFs — and the answer itself can be saved as a new wiki page (source: Andrej Karpathy's LLM Wiki Bye Bye RAG.md).

The pattern was originated by [[karpathy-bio|Andrej Karpathy]] and shared as a gist intended to be copy-pasted into LLM agents (source: llm-wiki.md).

## The key difference

**The wiki is a persistent, compounding artifact.** The cross-references are already there. The contradictions have already been flagged. The synthesis already reflects everything that has been read. The wiki keeps getting richer with every source added and every question asked (source: llm-wiki.md).

## Division of labor

- **The human** curates sources, directs analysis, asks good questions, and thinks about what it all means (source: llm-wiki.md).
- **The LLM** does everything else — summarizing, cross-referencing, filing, and bookkeeping (source: llm-wiki.md).

In practice, the author describes having the LLM agent on one side and Obsidian on the other. The LLM makes edits based on conversation, and the human browses results in real time. "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase." (source: llm-wiki.md)

## Why it works

The tedious part of maintaining a knowledge base is not the reading or thinking — it is the bookkeeping. Updating cross-references, keeping summaries current, noting contradictions, maintaining consistency. Humans abandon wikis because the maintenance burden grows faster than the value. LLMs do not get bored, do not forget to update a cross-reference, and can touch 15 files in one pass (source: llm-wiki.md).

## Prior art and critique

The pattern is not entirely new. Community discussion has connected it to earlier work on the **semantic web** and **knowledge graphs**, which also aimed to turn unstructured information into consistent, computable knowledge structures (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, CatNo2950). Since GPT-3.5, RAG-based knowledge retrieval has been widely deployed in enterprise (AWS, Atlassian, Google, Glean, Notion) and open-source projects (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, EntropyRX).

What distinguishes the LLM Wiki is the emphasis on **persistent, human-readable compilation** rather than on-the-fly retrieval. See [[community-reception]] for the full debate.

## Learning value tradeoff

A notable critique is that having an LLM build the wiki removes the cognitive benefit of organizing knowledge yourself. The counterargument: the value proposition differs depending on the use case — organizing existing scattered materials vs. learning new material from scratch are different problems (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, Silver_Temporary7312). See [[community-reception]] for details.

## Scale in practice

Karpathy's own research wiki at the time of his [[karpathy-thread|original Twitter thread]] contained approximately **100 articles and 400,000 words**. At this scale, the LLM was "pretty good about auto-maintaining index files and brief summaries" without needing fancy RAG infrastructure (source: Thread by @karpathy.md).

## Future directions

As a wiki grows, the natural desire is to explore **synthetic data generation + finetuning** — having the LLM "know" the data in its weights instead of just in context windows (source: Thread by @karpathy.md).

## Flexibility

The document is intentionally abstract. The exact directory structure, schema conventions, page formats, and tooling depend on the user's domain, preferences, and LLM of choice. Everything is optional and modular (source: llm-wiki.md).

## Related pages

- [[llm-wiki-source]]
- [[rag-vs-wiki]]
- [[architecture]]
- [[operations]]
- [[memex]]
- [[community-reception]]
- [[karpathy-bio]]
- [[criticisms]]
- [[karpathy-thread]]
- [[setup-guides]]
