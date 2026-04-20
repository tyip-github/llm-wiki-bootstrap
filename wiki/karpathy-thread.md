# Karpathy Twitter Thread (Source Summary)

**Summary**: Summary of Andrej Karpathy's original Twitter thread describing his personal LLM Wiki workflow, scale, and tools.

**Sources**: Thread by @karpathy.md

**Last updated**: 2026-04-14

---

## Overview

On April 2, 2026, [[karpathy-bio|Andrej Karpathy]] posted a Twitter thread describing his personal use of LLMs to build knowledge bases for research topics. This thread preceded the more detailed gist and catalyzed the broader discussion around the [[llm-wiki-pattern]] (source: Thread by @karpathy.md).

## Workflow details

Karpathy describes a six-part workflow (source: Thread by @karpathy.md):

1. **Data ingest**: Index source documents (articles, papers, repos, datasets, images) into a `raw/` directory. The LLM incrementally "compiles" a wiki of `.md` files with summaries, backlinks, concept articles, and cross-links. Uses [[obsidian|Obsidian]] Web Clipper to convert web articles to markdown, with a hotkey to download related images locally.

2. **IDE**: Uses [[obsidian|Obsidian]] as the frontend to view raw data, the compiled wiki, and derived visualizations. "The LLM writes and maintains all of the data of the wiki, I rarely touch it directly." Uses plugins like [[marp|Marp]] for slides.

3. **Q&A**: At scale (~100 articles, ~400K words), he can ask complex questions against the wiki. The LLM auto-maintains index files and brief summaries, avoiding the need for fancy RAG at this scale.

4. **Output**: Instead of text/terminal answers, the LLM renders markdown files, slideshows ([[marp|Marp]] format), or matplotlib images, all viewed in Obsidian. Outputs are often filed back into the wiki to enhance it for further queries.

5. **Linting**: Runs LLM "health checks" to find inconsistent data, impute missing data (with web searches), find interesting connections, and incrementally clean up the wiki.

6. **Extra tools**: Develops additional tools to process data, including a naive search engine (web UI + CLI for LLM use).

## Scale

His research wiki at the time of the thread contained approximately **100 articles and 400,000 words** (source: Thread by @karpathy.md).

## Future directions

Karpathy mentions the natural desire for **synthetic data generation + finetuning** as a wiki grows — having the LLM "know" the data in its weights instead of just in context windows (source: Thread by @karpathy.md).

## Key quote

> "I think there is room here for an incredible new product instead of a hacky collection of scripts." (source: Thread by @karpathy.md)

## Related pages

- [[llm-wiki-pattern]]
- [[llm-wiki-source]]
- [[karpathy-bio]]
- [[obsidian]]
- [[operations]]
- [[tooling]]
