---
layout: post
title: "The model barely matters"
date: 2026-08-30
series: agentic-skeleton
series_num: 1
series_title: The Agentic AI Skeleton
---

# The model barely matters

The industry line on AI coding is simple: pick the right model and your problems are solved. If not today's model, tomorrow's will do it.

50 hours and a production healthcare app later, I learned that the model barely matters.

I ran 12+ open-weight models through the same harness on the same codebase. The differences were marginal. I spent €15 on tokens total. That €15 wasn't an achievement — it was proof that the model was never the bottleneck.

External data backs this up:

- **[Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase)** on a multi-million-line codebase: token price is a poor predictor of actual task cost, and open-weight models handled the highest-difficulty tasks just fine.
- **[Veracode's 2026 survey](https://www.veracode.com/resources/analyst-reports/2026-genai-code-security-report/)**: model size doesn't improve code security, and coding-specialized models aren't safer than general ones.

The pattern is clear: model size and price don't predict outcomes for development tasks. Security doesn't improve with bigger models. Task completion doesn't require frontier models.

What _did_ matter was the environment I built around the model — the harness, the task scoping, and the documentation structure.

So stop agonizing over model selection. Pick any competent open-weight model, avoid lock-in to proprietary offerings, and move on. The model isn't where your time goes — and it shouldn't be where your attention goes either.

_Having freed yourself from the model question, the next thing to look at is the harness. That's the next piece._
