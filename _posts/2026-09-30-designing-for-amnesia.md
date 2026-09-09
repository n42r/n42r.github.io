---
layout: post
title: "Designing for amnesia"
date: 2026-09-30
series: agentic-skeleton
series_num: 4
series_title: The Agentic AI Skeleton
---

# Designing for amnesia

Designing your AI-assisted codebase so that every session starts from zero produces more reliable agents than managing session memory.

At some point I added a deliberately absurd line to my AGENTS.md: "I have a rare case of amnesia where at the end of each day I forget everything that took place." I removed it the next day. The design question it raised stayed: _what if I designed my entire setup so that forgetting everything between sessions is the norm?_

Last Tuesday I closed a task by appending two bullet points to NOTES.md and updating the body of a relevant issue, so I could pick it up next week from zero. That habit — externalize everything before closing a task — became a design principle. The amnesia line was a joke version of it. But it turned out to apply not just to me, but to AI agents and to anyone new onboarding to a project.

The café experiment made it real. I met a friend to talk AI. He knew nothing about the project beyond its elevator pitch. I opened a fresh agent session, handed him the laptop, and gave him a simple implementation task. Now both the human and the agent had amnesia. I watched from behind.

It was painful. The agent traversed irrelevant directories, read irrelevant files, and missed essential ones — like the compliance documentation it needed before touching an audit-logged event. My friend gave up trying to orient himself and prompted: "Give me a detailed implementation plan for task X." The agent's plan was built on a partial and partly wrong understanding of the codebase. Different models, even different fresh runs of the same model, explored the same codebase differently. Everything was left to chance.

We made changes — the kind a practitioner would recognize: moved most content from `AGENTS.md` into `docs/ARCHITECTURE.md`, split `AGENTS.md` into a system-wide file and a repo-level one, and added a navigation map pointing to just enough of the next level of relevant files (not all of them, for progressive disclosure reasons). Then we ran it again — a fresh session, a different model, and the prompt: "Welcome to the project." We watched where it got lost, made notes, fixed. A couple of iterations later, agents started navigating fluently and consistently across models and runs. Cold-starting went from a 15-minute hand-holding session to pointing at a GitHub issue and saying "welcome to the project."

It got boring. Boring in the best way: fewer surprises, fewer interventions, less rework, lower variance between sessions. Cross-model session replacement became a normal operating mode — I destroy the agent at the end of every session and start fresh the next day, sometimes with a different model entirely.

The documentation structure that emerged from this wasn't unique. I later found that OpenAI's February 2026 ["Harness engineering" case study](https://openai.com/index/harness-engineering/) had arrived at the same pattern: a short AGENTS.md used as a map rather than an encyclopedia, a structured `docs/` directory as the system of record, progressive disclosure. What I did on a €20/month budget in a regulated healthcare domain, they did at scale.

The simplest way to test your codebase for amnesia resistance: give a fresh agent one real task, say nothing else, and watch where it gets lost. Then fix that. Repeat with a different model. When it stops getting lost, you're done — for now.

_How you structure the documentation that makes that cold start reliable — the architecture behind the map — is the next piece._
