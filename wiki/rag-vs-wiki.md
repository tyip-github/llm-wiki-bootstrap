# RAG vs Wiki

**Summary**: A comparison of the traditional RAG (Retrieval-Augmented Generation) approach and the LLM Wiki pattern for working with document collections.

**Sources**: llm-wiki.md, Karpathy's LLM Wiki and why it feels kind of a game changer.md, Andrej Karpathy's LLM Wiki Bye Bye RAG.md, Andrej Karpathy's LLM Wiki is a Bad Idea.md, Andrej Karpathy Killed RAG. Or Did He? The LLM Wiki Pattern.md

**Last updated**: 2026-04-14

---

## RAG approach

In a typical RAG setup, the user uploads a collection of files, the LLM retrieves relevant chunks at query time, and generates an answer. Systems like NotebookLM, ChatGPT file uploads, and most RAG pipelines work this way (source: llm-wiki.md).

**Limitations:**
- The LLM rediscovers knowledge from scratch on every question (source: llm-wiki.md)
- There is no accumulation — nothing is built up between queries (source: llm-wiki.md)
- Subtle questions requiring synthesis across multiple documents force the LLM to find and piece together fragments every time (source: llm-wiki.md)

## Wiki approach

The [[llm-wiki-pattern]] takes a different approach. Instead of retrieving from raw documents at query time, the LLM incrementally builds a persistent wiki — compiling knowledge once and keeping it current (source: llm-wiki.md).

**Advantages:**
- Cross-references are pre-built (source: llm-wiki.md)
- Contradictions are already flagged (source: llm-wiki.md)
- Synthesis reflects all sources read to date (source: llm-wiki.md)
- Knowledge compounds with every source and every question (source: llm-wiki.md)

## Indexing at scale

At moderate scale (~100 sources, hundreds of pages), a simple index file (index.md) works well enough for the LLM to find relevant pages without needing embedding-based RAG infrastructure (source: llm-wiki.md). As the wiki grows, proper search tools like [[tooling|qmd]] can be added (source: llm-wiki.md).

## "RAG is a solved problem" perspective

Some community members argue that personal RAG over a few hundred documents has been a solved problem since GPT-3.5, with countless services (AWS, Atlassian, Google, Glean, Notion) and open-source repos built around it (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, EntropyRX).

However, RAG systems face persistent challenges: hallucination risk, and the need for document authority, recency, and relevance scoring that cannot be deterministically solved by an LLM alone (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, EntropyRX). The wiki approach sidesteps some of these by compiling knowledge upfront, though it introduces its own challenge of [[community-reception|staleness and silent drift]].

One commenter also noted that a wiki's link-and-tag structure (as in Obsidian) creates a graph of edges and nodes, which is fundamentally different from folder-based filing — the secondary classification problem that pure folder systems struggle with (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, Fetlocks_Glistening, FlyingNarwhal).

## Stateless vs stateful

Another way to frame the difference: RAG is **stateless** in practice — each query is independent, nothing compounds. The LLM Wiki is **stateful** — knowledge builds on top of previous knowledge (source: Andrej Karpathy's LLM Wiki Bye Bye RAG.md).

- RAG: Search → Answer → Reset
- LLM Wiki: Read → Organize → Link → Improve → Reuse

Or as an analogy: "With RAG, you cook every time you are hungry. With LLM Wiki, you build a kitchen that keeps improving its recipes." (source: Andrej Karpathy's LLM Wiki Bye Bye RAG.md)

## RAG's strengths over wiki

Critics have identified several areas where RAG retains clear advantages over the wiki approach. See [[criticisms]] for full detail.

- **Error isolation**: With RAG, each answer starts fresh from source documents. Mistakes don't persist or compound across queries (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).
- **Traceability**: RAG answers trace directly to source documents. Wiki answers come from a mix of generated pages, making verification harder (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).
- **Cost profile**: RAG does the heavy work at query time. The wiki shifts cost to ingestion and maintenance, which increases over time (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).
- **Changing data**: RAG always queries the latest data. The wiki requires reprocessing when sources change (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## "Just a cache layer"

The community is split on how to frame the pattern: half thinks RAG is officially dead, the other half thinks Karpathy just gave a fancy name to a cache layer. Both sides have a point. The real insight may not be "RAG bad, wiki good" but that knowledge should compound, not evaporate (source: Andrej Karpathy Killed RAG. Or Did He? The LLM Wiki Pattern.md).

## Scalability concerns

The LLM Wiki pattern is well-suited to personal use, but its scalability to enterprise settings is unproven. No one has publicly tested it at 100,000+ documents. At that scale, the index-based navigation may break down and the maintenance overhead of updating interlinked pages could become a bottleneck (source: Andrej Karpathy's LLM Wiki Bye Bye RAG.md, commenter). This contrasts with RAG systems, which have been deployed at enterprise scale by multiple vendors (source: Karpathy's LLM Wiki and why it feels kind of a game changer.md, EntropyRX).

## Related pages

- [[llm-wiki-pattern]]
- [[architecture]]
- [[operations]]
- [[community-reception]]
- [[criticisms]]
