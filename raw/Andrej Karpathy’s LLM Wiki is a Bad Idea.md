---
title: "Andrej Karpathy’s LLM Wiki is a Bad Idea"
source: "https://medium.com/data-science-in-your-pocket/andrej-karpathys-llm-wiki-is-a-bad-idea-8c7e8953c618"
author:
  - "[[Mehul Gupta]]"
published: 2026-04-11
created: 2026-04-14
description: "Andrej Karpathy’s LLM Wiki is a Bad Idea Why LLM-Wiki will fail ? Everyone is suddenly excited about this new idea called LLM-Wiki. The pitch sounds very clean. Instead of searching documents again …"
tags:
  - "clippings"
---
[Mastodon](https://me.dm/@mehulgupta_7991)

## [Data Science in Your Pocket](https://medium.com/data-science-in-your-pocket?source=post_page---publication_nav-60130df77e02-8c7e8953c618---------------------------------------)

[![Data Science in Your Pocket](https://miro.medium.com/v2/resize:fill:38:38/1*azLPGT6SA58kykLPlca3TQ.jpeg)](https://medium.com/data-science-in-your-pocket?source=post_page---post_publication_sidebar-60130df77e02-8c7e8953c618---------------------------------------)

YouTube: [https://www.youtube.com/@datascienceinyourpocket](https://www.youtube.com/@datascienceinyourpocket)

## Why LLM-Wiki will fail?

![](https://miro.medium.com/v2/resize:fit:1400/format:webp/0*8p6JHHOuen0LzmEp)

Photo by Luke Chesser on Unsplash

Everyone is suddenly excited about this new idea called LLM-Wiki. The pitch sounds very clean. Instead of searching documents again and again like RAG, the model builds its own structured knowledge base, like a personal Wikipedia.

> At first glance, it feels like the next step. Smarter, faster, more organized. You upload information once, and the system keeps improving itself over time. It sounds like how humans learn.

But once you slow down and think about it, the cracks start showing.

> This is not a “bye bye RAG” moment. In fact, LLM-Wiki can very easily turn into a messy and unreliable system.

## The biggest problem: mistakes don’t disappear

### With RAG, every answer starts fresh.

The model goes back to the original documents each time. Even if it makes a mistake once, the next query has a chance to correct it because the source is still the same.

> LLM-Wiki changes that completely.

Here, the model reads documents, creates pages, links them, and stores that as knowledge. But what if the model misunderstands something while doing this? That mistake doesn’t just stay local. It gets saved, reused, and connected to other pages.

> Over time, a small misunderstanding can quietly spread across the system. The wiki still looks clean and structured, but inside, parts of it can be wrong.

## It turns small hallucinations into system-level issues

> LLMs are known to sometimes fill gaps or make assumptions. In a normal setup like RAG, that’s manageable. A wrong answer is just one wrong answer.

### In LLM-Wiki, that same behavior becomes much more dangerous.

The model might create pages that were never directly supported by the source. It might connect ideas that sound logical but are not actually true. And because everything is written in a structured, Wikipedia-like format, it feels trustworthy.

> pages can be generated without solid backing
> 
> connections can look logical but be incorrect
> 
> errors become part of the system, not just outputs

So now you’re not dealing with random mistakes. You’re dealing with organized, persistent mistakes.

## You slowly lose the original truth

> To build a wiki, the model has to summarize and compress information. But compression always removes detail.

Things like edge cases, exact wording, and subtle differences often don’t survive this process. These details may not matter for simple questions, but they are critical in serious use cases.

> With RAG, the raw documents are always there. You can trace things back, read the original text, and verify.

With LLM-Wiki, you are one or two steps removed from the source. You are relying on the model’s interpretation of the source, not the source itself.

## Updating knowledge sounds easy, but isn’t

> The idea suggests that the system will keep updating itself as new data comes in. In theory, this sounds powerful. In practice, it is messy.

Knowledge is deeply connected. One small update in one area can affect many related pages. Now the model has to update multiple entries, fix links, and ensure everything stays consistent.

> one change can impact many pages
> 
> links between concepts can break
> 
> contradictions can appear quietly

Doing this perfectly is hard even for humans. Expecting an LLM to maintain this cleanly over time is risky.

## You lose clear traceability

One of the biggest strengths of RAG is that it is easy to trace answers back to sources. You can see exactly which document the answer came from. LLM-Wiki breaks this clarity.

> Answers now come from a mix of generated pages, summaries, and linked ideas. When you try to verify something, it becomes difficult to answer a simple question: where did this come from?

This is a serious problem for systems where trust matters, like research or business use cases.

## It looks efficient, but shifts the cost

LLM-Wiki feels efficient when you ask questions, because the heavy work is already done. But that work doesn’t disappear. It just moves earlier in the pipeline.

## Get Mehul Gupta’s stories in your inbox

Join Medium for free to get updates from this writer.

Every new document needs to be processed, summarized, linked, and merged into the existing structure. This takes time and compute.

- ingestion becomes heavy
- updates become expensive
- maintenance keeps increasing

### RAG, in comparison, keeps things simple and handles most of the work at query time.

## It does not scale cleanly

With a small number of documents, LLM-Wiki feels impressive. Everything is neat and connected. But as the system grows, complexity grows faster.

> You start seeing duplicate pages, messy links, and overlapping concepts. The structure becomes harder to manage, and inconsistencies start creeping in.

At that point, it becomes less like a clean Wikipedia and more like a knowledge base with no editors.

## It struggles with changing data

If your data changes frequently, LLM-Wiki becomes even harder to manage. Since it relies on pre-built pages, updates require reprocessing parts of the system.

RAG handles this better because it always goes back to the latest data. It doesn’t depend on a pre-constructed structure.

## Most problems don’t need this complexity

***A lot of real-world queries are simple. They don’t require deep linking across dozens of concepts. They just need accurate information from a few sources.***

RAG already handles these cases well.

LLM-Wiki introduces a layer of complexity that often doesn’t add proportional value.

## What actually makes sense

The better direction is not choosing one over the other.

Use RAG for accuracy and grounding. Add small layers of structured memory where it helps. But avoid turning the entire system into an auto-generated wiki that tries to manage everything.

## Final thought

> LLM-Wiki is a clever idea. It shows a possible future where LLMs don’t just answer questions but build knowledge systems.

But right now, it comes with serious trade-offs. Errors can compound, truth becomes harder to verify, and systems become complex to maintain.

A clean structure can feel impressive, but it does not guarantee correctness. And in the end, correctness matters more than structure.

## Responses (4)

Write a response[What are your thoughts?](https://medium.com/m/signin?operation=register&redirect=https%3A%2F%2Fmedium.com%2Fdata-science-in-your-pocket%2Fandrej-karpathys-llm-wiki-is-a-bad-idea-8c7e8953c618&source=---post_responses--8c7e8953c618---------------------respond_sidebar------------------)

```c
Most of these concerns are about the pattern in theory — implementations have moved past them. For example, github.com/Oshayr/LLM-Wiki keeps raw sources immutable, runs a fact-checker agent, assigns confidence tiers to every page, auto-merges…
```

12

```c
Your first point suggests the system is flawed because malicious or mislinked articles can corrupt the output. However, this is simply the 'Garbage In, Garbage Out' principle, which applies to RAG systems just as much as it does to LLM Wiki.
```

3

```c
That’s why I built sessionfs.dev
```

2