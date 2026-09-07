---
layout: post
title: "The harness trap"
date: 2026-09-15
series: agentic-skeleton
series_num: 2
series_title: The Agentic AI Skeleton
---

# The harness trap

I started with 6 harnesses, 20 skills, and 8 plugins. I ended with one harness, two skills, and a working production app.

The **agent harness** is the most promising development to come out of the LLM space. The idea is dead simple: put the agent in a loop, give it tools, let it execute commands on your computer.

50 hours of agentic coding showed me that the harness moved outcomes more than the model. External benchmarks confirm it:

- **[Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase)**: same model, different harness, 2x cost difference. The modular harness (Pi) won.
- **[Composio's Comparison](https://composio.dev/content/best-ai-agent-harnesses)**: same model, 8 harnesses, 20-point spread. Again, a modular harness won.

Same model, different harnesses, massive variance. When you hold the model constant, the harness accounts for most of the outcome — not the other way around.

But benchmarks aren't why I landed where I did. My first attempt was a fully-featured, black-box harness. I gave it a 500-line spec, hit enter, and watched messages fly. Ten minutes later, it produced something that looked like a complete app. I opened the browser. It broke on first navigation. I had no idea what it generated, no visibility into what it tried, no way to debug where it went wrong.

That's the hidden tax of fully-featured, black-box harnesses. They make assumptions about how you work, bundle you into their model and their workflow, and give you no levers to pull when things break. The lock-in isn't just vendor lock-in — it's assumptions baked into the product that you can't see or override. Databricks' benchmark ends on a similar note:

> "We've always been wary of lock-in, not just to vendors, but to assumptions that make teams less flexible over time."

I switched to a modular harness — one that gave me visibility into what the agent was doing and control over what to add. The first few days were rough: I hit an issue, couldn't find the built-in fix, and had to understand the problem myself. But that understanding was the point. Because the harness was bare-bones and modular, I slowly adapted it to my stack, my conventions, my codebase. What I ended up with looked like an old-school software engineering setup.

The pattern is the same as with models: more features don't predict better outcomes. The harness that gives you control and visibility beats the one that offers convenience — because convenience hides the work, and the work is where the value is.

Start with a modular harness that gives you visibility and control. Add only what proves valuable. That's the hard part — not because the setup is hard to configure, but because it leaves you exposed. There's no safety net of fancy features to catch a poorly scoped task. And that's the point.

_What you do with that exposure — how you scope tasks and structure context — is the next piece._
