---
title: "Karpathy’s LLM Wiki and why it feels kind of a game changer"
source: "https://www.reddit.com/r/learnmachinelearning/comments/1shfkx5/karpathys_llm_wiki_and_why_it_feels_kind_of_a/"
author:
  - "[[knlgeth]]"
published: 2026-04-10
created: 2026-04-14
description: "I’ve been seeing Andrej Karpathy’s idea of an LLM Wiki a lot lately, and the more I think about it, the more it feels like a genuinely power"
tags:
  - "clippings"
---
I’ve been seeing Andrej Karpathy’s idea of an LLM Wiki a lot lately, and the more I think about it, the more it feels like a genuinely powerful shift in how we handle knowledge.

The idea of turning scattered sources into a structured, self-updating system that you can actually query and build on just makes too much sense. Instead of constantly saving links, notes, and docs that never get revisited, everything becomes part of a living knowledge base that improves over time.

It honestly feels like this could reduce a huge chunk of my workload, especially around research, organization, and context switching. Rather than manually managing information, you let the system handle the heavy lifting while you focus on using the insights.

I’m curious if anyone has come across solid projects or GitHub repos that really capture the core loop of this idea and execute it well in practice.

Would really appreciate any suggestions:)

---

## Comments

> **muhmeinchut69** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofcczny/) · 131 points
> 
> seems sus, are you karpathy's clawbot?
> 
> > **ladjanszki** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofew4ff/) · 7 points
> > 
> > no, I'm the bot promoting the wiki... /s
> > 
> > but seriously I can also relate to OPs great expectations, Im also reading about Karpathy's concept.
> > 
> > > **muhmeinchut69** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofexsv4/) · 7 points
> > > 
> > > Actually, I later found out that OP really is a clawbot, the account is the moderator of a subreddit for a managed clawbot service, and mostly posts obvious AI posts there.

> **CatNo2950** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofci6gv/) · 55 points
> 
> This idea has been around for a long time ([semantic web](https://www.reddit.com/search/?q=semantic+web&cId=9034b0e1-3d14-4b9e-9e08-7aeff8423636&iId=21d9437b-ac92-4239-bab3-1994ed83bd0c) , [knowledge graphs](https://www.reddit.com/search/?q=knowledge+graphs&cId=4b8141cb-0d53-475b-8e42-d646811ec8b5&iId=aae5f714-6123-430b-8dfd-6181bdfd6f81) , etc). The tricky part isn’t organizing information - it’s reliably turning messy natural language into a consistent, non-contradictory knowledge structure you can actually compute over. LLMs help, but they don’t really solve that core problem yet.
> 
> > **Thrumpwart** · [2026-04-11](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofk59qv/) · 3 points
> > 
> > Constrained outputs and agent harnesses could help. All the tools are there - someone just has to commit to the time and resources to lay the foundation.

> **Abject-Excitement37** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofck9he/) · 75 points
> 
> llm building your wiki is worthless for your growth, you gain anything by building it itself
> 
> > **elprogramatoreador** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofcl7d0/) · 10 points
> > 
> > Good advice
> > 
> > **vladlearns** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofcocui/) · 4 points
> > 
> > this  
> > I wish more people would understand this

> **lordbrocktree1** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofcgvb4/) · 28 points
> 
> I’m confused how people think this is such a ground breaking revolution. We have been working on an internal capability at my company for the last year for internal use. We were just having in the next few months. I couldn’t see much else out like it. And thought it was so obvious, that I was surprised there weren’t already solutions for it when I looked last year.
> 
> > **Entire\_Ad\_6447** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofd1irl/) · 6 points
> > 
> > Because a big name in the field said it and most people on this sub are lemings.

> **Fetlocks\_Glistening** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofch6df/) · 13 points
> 
> Isn't a wiki essentially a classic folders-subfolders filing system? Which captures one primary classification criterion at time of filing, but not the myriad of secondary classification criteria for which you need a secondary index. Bringing you back to [embeddings](https://www.reddit.com/search/?q=embeddings+machine+learning&cId=e2a746a7-51f7-4caa-bd28-b9d21854cd6a&iId=27e88070-2ce0-41de-97f6-d286f057dd9a) ?
> 
> > **FlyingNarwhal** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofe6e5b/) · 6 points
> > 
> > Karpathy uses [Obsidian](https://www.reddit.com/search/?q=Obsidian&cId=77a49ef6-b6fd-4289-886b-7f381d00ef05&iId=19ce0b57-c5ea-423a-a855-2024ab791de4) , which mostly relies upon file links and tags, like a normal wiki does. this isn't a folder-subfolder, though that's part of the structure. It creates a knowledge base that's explorable via edges and nodes, as well as categoriziation via tags & folders.

> **Karyo\_Ten** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofcaxl9/) · 5 points
> 
> I use [DeepWiki](https://www.reddit.com/search/?q=DeepWiki&cId=6cf13c3d-59f8-480b-95a7-e46dded875af&iId=96f2f08c-ea17-4ac0-85cf-89ed20f76eb8)

> **Silver\_Temporary7312** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofcznxa/) · 5 points
> 
> the pushback here is legit tbh. there's actual value in the struggle of organizing knowledge yourself, not just having a system do it. that's when you really learn the material.
> 
> that said the appeal is different if you have tons of scattered notes and pdfs already and just want a better way to query them. not the same as building from scratch though, two completely different use cases.
> 
> either way the hype usually ignores the learning part. building systems teaches you way more than using them, karpathy's version or your own wiki.

> **fisebuk** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofde4qz/) · 5 points
> 
> the validation problem is actually the interesting bit imo. when you're building systems that parse information, you hit the same consistency issues we see in security research - sources contradict, context gets lost, everything looks solid until you pressure test it. approaching frameworks by mapping out failure modes and edge cases first accelerates understanding way more than passive organization. gives you real mental hooks instead of just organized notes

> **ataeff** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofdi4ah/) · 8 points
> 
> karpathy? LLM wiki? another "let me explain..."
> 
> 2017: "Let me explain backprop"  
> 2019: "Let me explain GPT"  
> 2021: "Let me explain GPT-2"  
> 2023: "Let me explain GPT from scratch"  
> 2024: "Let me explain nanoGPT"  
> 2025: "Let me explain nanochat"  
> 2026: "Let me explain GPT-2 in most atomic way: microgpt.py" ← you are here  
> again 2026: "Let me explain... Alright, here's a WIKI"  
> 2027: "nanoAGI from scratch" (spoiler: it'll be GPT-2 with more layers)

> **Beneficial\_Jello9295** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofea8tg/) · 4 points
> 
> I fail to understand how is this that much different to using stuff like NotebookLM

> **GifCo\_2** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofcufwu/) · 3 points
> 
> It's not even novel there were already solutions like this. It's interesting, and semi useful nothing more.

> **lxe** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofdwbf4/) · 3 points
> 
> Spin up a cron to take your agent sessions and process them into a series of markdown files. Nothing groundbreaking here.

> **manoman42** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofec90f/) · 2 points
> 
> [HTTPS://Github.com/rtalabs-ai/aura-research](https://github.com/rtalabs-ai/aura-research)

> **EntropyRX** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofeubr1/) · 2 points
> 
> This is nothing new lol. Since gpt3.5 the FIRST problem each and every business tried to solve was knowledge retrieval consumed in a Q&A type of chatbot, also known as RAG. There are COUNTLESS of services built around this very idea, from expensive enterprise ones (AWS, atlassian, Google, glean, notion, ….) to scrappy GitHub repos. Each of them starts with a form of ingestion with connectors for different data sources where you create a knowledge base (it can be as a simple as a folder, up to real search engines).
> 
> The problem with these systems is that there is ALWAYS the risk of hallucinations, and generally speaking the retrieval of relevant sources is the critical part and it can’t be simply delegated to the LLM. You need a concept of document authority, recency and relevance that can’t be deterministically solved by an LLM.
> 
> That being said, if you have a few hundreds docs and you want to use them to build your personal RAG, that’s a solved problem and it has been solved for years now. Pretty much any service allow you to do that.

> **ultrathink-art** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/offbkrr/) · 2 points
> 
> Staleness is the gap nobody addresses upfront. The LLM can't know when a fact has changed, so it returns outdated context with full confidence — silent drift is the real failure mode. What makes this durable in practice is explicit freshness metadata alongside embeddings: source version, ingestion timestamp, explicit TTLs.

> **Ghiren** · [2026-04-10](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/offhmwh/) · 2 points
> 
> I've mainly been using the initial gist that Karpathy posted. There's a lot of value interacting with the agent/wiki and watching how it works. Building it is an iterative process so you can shape how it learns, especially since what what it learns is written down an AGENTS.md file.
> 
> Here are a few features that I've added (or asked the LLM to add for me)
> 
> 1. Dates and timestamps on the logs to ensure that they're in chronological order. When I tried switching between Gemini and Codex agents, the instruction that entries should be appended was lost.
> 2. Git is part of the process. I have a section in my agent file that describes git hygiene. It's easier to ask the agent to roll back a change than to fix it. Anything worth adding to the log is followed by a git commit.
> 3. Listing things in an index.md file looks like it saves a lot of context space. I haven't written explicit instructions for it yet but I think that for very large wikis, this could become a hierarchical structure of indexes based on interconnected groups of pages. (EDIT: Categories appear to be working great. I added instructions for it to the Ingest and Research sections of my agent instructions. Category indices are treated like any other wiki page.)
> 4. index.md could also be adapted to MCP so your agent could index a large array of tools without filling your context window with tool descriptions. Each MCP server would be its own wiki page that your agent accesses when it needs those specific tools.

> **lewd\_peaches** · [2026-04-11](https://reddit.com/r/learnmachinelearning/comments/1shfkx5/comment/ofihjzl/) · 2 points
> 
> It's great to see someone organizing all that knowledge into one place. I find myself constantly going back to Karpathy's lectures, so a wiki could be really useful. What specific parts are you finding most game-changing?