---
layout: post
title: "The hidden tax of speed"
date: 2026-09-23
series: agentic-skeleton
series_num: 3
series_title: The Agentic AI Skeleton
---

# The hidden tax of speed

The seduction of AI coding is the same as the seduction of any credit card: you get the purchase now, the bill comes later, and the interest compounds.

My first one-shot attempt — 500-line spec, complete-looking app, broke on first navigation — taught me the first lesson.  That was the bill arriving immediately — not later, which is the best case for learning.

Later, building incrementally, I wrote a 500-line spec to implement a _single major feature_ — about 1/10 of the original scope. The spec was the _same size_. The scope was _10x smaller_. Now I could debug, extend, and trust the result.

The session ratio shift tells the story. I started at 20% pre-coding, 30% coding, 50% debugging and tuning. I now spend 60% pre-coding, 20% coding, 20% post-coding. The coding step got shorter because the pre-coding step got serious. The debugging step collapsed because the work was scoped before the agent touched it.

Halfway through development, a feature required a minor narrowing in one schema element. I was short on time, skipped the architecture review, and let the agent proceed. TypeScript validators failed. The agent started liberally rewriting the domain contracts to make the types pass — entering a dependency hell of its own making. I pulled the plug, tried a frontier model (50× the cost), and got fancier-looking hallucinations. I closed both agents, took out paper and pen, and solved it by hand — a subtle refactoring that touched two contracts. These were contracts I had written myself: 200 lines of Zod schemas, two weeks of careful work I was tempted to skip, the machine-checkable source of truth every agent worked from. 

One line of schema change stalled the entire pipeline. If a one-line change to contracts I wrote myself could spiral, I can only imagine what would have happened if an LLM had written them.

External data confirms the pattern is not mine alone. A [2026 study](https://arxiv.org/html/2603.28592v1) of 304,000 AI-authored commits across 6,275 GitHub repositories found that 24% of issues AI introduced — code smells, bugs, security vulnerabilities — still survived in the latest revision, persisting as long-term maintenance costs. The [2025 DORA report](https://dora.dev/research/2025/dora-report/) found that while AI adoption improves delivery throughput, it continues to increase delivery instability — and the instability is not offset by the speed gains. It still damages product performance and burnout, "which can ultimately negate any perceived gains in throughput." MIT's Armando Solar-Lezama [put it precisely](https://www.wsj.com/articles/ai-is-writing-code-now-for-companies-that-is-good-and-bad-6f19ecdc): AI is "a brand new credit card that is going to allow us to accumulate technical debt in ways we were never able to do before." Everyone feels more productive. The cost is what compounds.

I now evaluate coding sessions by how much genuine design work they force me to do upfront. If the pre-coding step isn't cognitively heavy — decisions, architecture, tradeoffs — I'll pay for it downstream. Every time. I added a line to my root AGENTS.md: "30 seconds of discussion beats 30 minutes of wrong implementation."

AI is a long stick that extends your arm, not the arm itself. When in doubt, do more work beforehand. The bill always comes — the only question is whether you pay it in design or in debugging.

