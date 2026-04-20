---
title: "Andrej Karpathy Killed RAG. Or Did He? The LLM Wiki Pattern"
source: "https://pub.towardsai.net/andrej-karpathy-killed-rag-or-did-he-the-llm-wiki-pattern-7824d876e790"
author:
  - "[[Mandar Karhade]]"
  - "[[MD. PhD.]]"
published: 2026-04-08
created: 2026-04-14
description: "Andrej Karpathy Killed RAG. Or Did He? The LLM Wiki Pattern 5,000 stars in 48 hours. A GitHub Gist. No code. Just an idea file. And the entire AI community lost its collective mind. TLDR Andrej …"
tags:
  - "clippings"
---
[Mastodon](https://me.dm/@ithinkbot)

## [Towards AI](https://pub.towardsai.net/?source=post_page---publication_nav-98111c9905da-7824d876e790---------------------------------------)

[![Towards AI](https://miro.medium.com/v2/resize:fill:38:38/1*JyIThO-cLjlChQLb6kSlVQ.png)](https://pub.towardsai.net/?source=post_page---post_publication_sidebar-98111c9905da-7824d876e790---------------------------------------)

We build Enterprise AI. We teach what we learn. Join 100K+ AI practitioners on Towards AI Academy. Free: 6-day Agentic AI Engineering Email Guide: [https://email-course.towardsai.net/](https://email-course.towardsai.net/)

## 5,000 stars in 48 hours. A GitHub Gist. No code. Just an idea file. And the entire AI community lost its collective mind.

**TLDR**

- Andrej Karpathy published a GitHub Gist describing “LLM Wiki,” a pattern where the LLM builds and maintains a persistent, compounding markdown knowledge base instead of re-retrieving documents on every query like traditional RAG.
- The architecture has three layers: raw sources (immutable), a wiki (LLM-maintained markdown with cross-references), and a schema (configuration directing agent behavior). No vector database required at personal scale.
- The community is split: half thinks RAG is officially dead, the other half thinks Karpathy just gave a fancy name to a cache layer. Both sides have a point.
- The real insight isn’t “RAG bad, wiki good.” It’s that knowledge should compound, not evaporate. And LLMs are finally good enough at bookkeeping to make that practical.
- Enterprise scalability is the elephant in the room: no RBAC, no ACID transactions, no concurrency controls. This is a personal knowledge weapon, not an enterprise platform. Yet.

[**Free Link**](https://medium.com/towards-artificial-intelligence/7824d876e790?sk=9c06eac415393ca020d4f777fb6aaad2) for everyone: **Clap 50, Follow and Subscribe to me.** Follow the **publication**. Join Medium to support other writers too! Cheers

***Please subscribe to my new profile*** [***https://medium.com/@ThisWorld***](https://medium.com/@ThisWorld) *where I am covering* ***Health tech, Global tech, and AI Governance*** *through multi-part deep investigative articles.*

**Link to the Gist:**

## A Gist That Built The Product

Andrej Karpathy, the man who taught the world how neural networks actually work with his Stanford lectures, who co-founded OpenAI, who built Tesla’s Autopilot vision stack, who left OpenAI (again) and has been quietly shipping open-source gold ever since; he dropped a GitHub Gist. Not a repo. Not a framework. Not a library with 47 dependencies and a YAML config that makes you question your career choices.

## Create an account to read the full story.

The author made this story available to Medium members only.  
If you’re new to Medium, create a new account to read this story on us.

[Continue in app](https://play.google.com/store/apps/details?id=com.medium.reader&referrer=utm_source%3Dregwall&source=-----7824d876e790---------------------post_regwall------------------)

Or, continue in mobile web

Already have an account? [Sign in](https://medium.com/m/signin?operation=login&redirect=https%3A%2F%2Fpub.towardsai.net%2Fandrej-karpathy-killed-rag-or-did-he-the-llm-wiki-pattern-7824d876e790&source=-----7824d876e790---------------------post_regwall------------------)[Last published just now](https://pub.towardsai.net/rag-chunking-that-works-semantic-splitting-overlap-and-eval-driven-tuning-530fbb25b613?source=post_page---post_publication_info--7824d876e790---------------------------------------)

We build Enterprise AI. We teach what we learn. Join 100K+ AI practitioners on Towards AI Academy. Free: 6-day Agentic AI Engineering Email Guide: [https://email-course.towardsai.net/](https://email-course.towardsai.net/)

## Responses (6)

Write a response[What are your thoughts?](https://medium.com/m/signin?operation=register&redirect=https%3A%2F%2Fpub.towardsai.net%2Fandrej-karpathy-killed-rag-or-did-he-the-llm-wiki-pattern-7824d876e790&source=---post_responses--7824d876e790---------------------respond_sidebar------------------)

```c
The LLM does the summarization? LLM summaries are notorious for hallucinations, even with the best models. Meanwhile, this system requires the LLM to constantly update the summaries, compounding the hallucination issue many fold with each and every…
```

12

```c
My god this madness keeps on going. If this could work don’t you think notion or any other database tool would have already implemented it. You are still dependable on the same old LLMs that cannot think for you and cannot make decisions of what is…
```

2

```c
This seems like an argument for graph RAG.
```

1