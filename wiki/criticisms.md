# Criticisms

**Summary**: Arguments against the LLM Wiki pattern, covering error compounding, truth compression, update complexity, traceability loss, cost shifting, and scaling challenges.

**Sources**: Andrej Karpathy's LLM Wiki is a Bad Idea.md, Andrej Karpathy Killed RAG. Or Did He? The LLM Wiki Pattern.md

**Last updated**: 2026-04-14

---

## Overview

While the [[llm-wiki-pattern]] has generated excitement, several detailed critiques have been published arguing that it introduces serious trade-offs. The most thorough critique comes from Mehul Gupta — notably the same author who wrote the enthusiastic "Bye Bye RAG" explainer — who reversed his position in a follow-up article (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## Error compounding

With [[rag-vs-wiki|RAG]], every answer starts fresh from the original documents. Even if the model makes a mistake once, the next query has a chance to correct it. In an LLM Wiki, the model reads documents, creates pages, links them, and stores that as knowledge. If it misunderstands something, that mistake gets saved, reused, and connected to other pages. Over time, a small misunderstanding can quietly spread across the system (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

This turns small hallucinations into system-level issues. Pages can be generated without solid backing, connections can look logical but be incorrect, and errors become part of the system rather than isolated outputs (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## Truth compression

To build a wiki, the model must summarize and compress information. Compression always removes detail — edge cases, exact wording, and subtle differences often do not survive. With RAG, the raw documents are always there to trace back to and verify. With an LLM Wiki, you are one or two steps removed from the source, relying on the model's interpretation (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## Update cascading

Knowledge is deeply connected. One small update in one area can affect many related pages. The model must update multiple entries, fix links, and ensure consistency. Doing this perfectly is hard even for humans (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

Potential consequences:
- Links between concepts can break
- Contradictions can appear quietly
- Pages can fall out of sync

## Traceability loss

One of the biggest strengths of RAG is that answers trace directly back to source documents. In an LLM Wiki, answers come from a mix of generated pages, summaries, and linked ideas. When trying to verify something, it becomes difficult to answer: where did this come from? This is a serious problem for systems where trust matters, like research or business use cases (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## Cost shifting

The wiki feels efficient at query time because the heavy work is already done. But that work does not disappear — it moves earlier in the pipeline (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md):

- Ingestion becomes heavy
- Updates become expensive
- Maintenance keeps increasing

RAG, by comparison, keeps things simple and handles most of the work at query time (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## Scaling challenges

With a small number of documents, the wiki feels impressive. But as the system grows, complexity grows faster. Duplicate pages, messy links, and overlapping concepts emerge. The structure becomes harder to manage, and inconsistencies creep in (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

No one has publicly tested the pattern at 100,000+ documents (source: Andrej Karpathy's LLM Wiki Bye Bye RAG.md, commenter).

## Enterprise gaps

The LLM Wiki pattern lacks enterprise-grade features: no RBAC (role-based access control), no ACID transactions, no concurrency controls. It is described as "a personal knowledge weapon, not an enterprise platform" (source: Andrej Karpathy Killed RAG. Or Did He? The LLM Wiki Pattern.md).

## Changing data

If data changes frequently, the wiki becomes harder to manage since it relies on pre-built pages. Updates require reprocessing parts of the system. RAG handles this better because it always goes back to the latest data (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## Counterarguments

- The "garbage in, garbage out" principle applies to RAG just as much as to LLM Wiki — malicious or mislinked articles corrupt any system (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md, commenter).
- Implementations have moved past some of these concerns: e.g. keeping raw sources immutable, running fact-checker agents, assigning confidence tiers to pages (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md, commenter).
- The original [[llm-wiki-pattern]] already includes [[operations|lint operations]] to catch contradictions, orphan pages, and stale claims (source: llm-wiki.md).

## Recommended middle ground

Use RAG for accuracy and grounding. Add small layers of structured memory where it helps. But avoid turning the entire system into an auto-generated wiki that tries to manage everything (source: Andrej Karpathy's LLM Wiki is a Bad Idea.md).

## Related pages

- [[llm-wiki-pattern]]
- [[rag-vs-wiki]]
- [[operations]]
- [[community-reception]]
