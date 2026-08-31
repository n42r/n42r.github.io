---
layout: post
title: "The harness matters more than the model"
date: 2026-09-15
series: agentic-skeleton
series_num: 2
series_title: The Agentic AI Skeleton
---

# The harness matters more than the model

I started with 6 harnesses, 20 skills, and 8 plugins. I ended with one harness, two skills, and a working production app.

The **agent harness** is the most promising development to come out of the LLM space. The idea is dead simple: put the agent in a loop, give it tools, let it execute commands on your computer.

50 hours of agentic coding showed me that the harness moved outcomes more than the model. External benchmarks confirm it:

- **[Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase)**: same model, different harness, 2x cost difference. The minimal harness (Pi) won.
- **[Composio's Comparison](https://composio.dev/content/best-ai-agent-harnesses)**: same model, 8 harnesses, 20-point spread. Again, a minimal harness won.

The mechanism is context management. Databricks found that Pi sent roughly three times less context per turn than native harnesses like Claude Code or Codex. A simpler harness doesn't let the model wander — it keeps the working set tight, which means fewer tokens, fewer round-trips, and less noise competing with the actual task. The harness isn't a UI preference. It's a context management decision, and context is the bottleneck.

Which is why the counterintuitive part isn't just that minimal harnesses win. It's that adding features makes things worse.

I had agents getting stuck in infinite loops, so I spent hours building an extension to detect them. The extension caught false positives. I spent more time dealing with those than with the original loops. I deleted it. The fix wasn't more tooling — it was shorter tasks and closer oversight.

I installed 30 skills. Two were helpful (`gdpr-compliant` and `pre-mortem`). The rest deteriorated performance. I removed them.

The pattern is the same one as with models: more features don't predict better outcomes. The harness that forces discipline beats the one that offers convenience.

Start minimal. Add only what proves valuable. That's the hard part — not because minimal is hard to configure, but because it leaves you exposed. There's no safety net of fancy features to catch a poorly scoped task. And that's the point.

_How you scope tasks and structure context — that's the next piece._

