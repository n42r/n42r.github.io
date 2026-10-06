---
layout: post
title: "The model barely matters"
date: 2026-10-06
series: agentic-skeleton
series_num: 1
series_title: The Agentic AI Skeleton
image: /assets/img/posts/mode-barely-matters.svg
image_alt: Two rows of equal sized similar looking circles 
---

The industry line on AI coding is simple: pick the right model and your problems are solved. If not today's model, tomorrow's will do it. And whichever it is, make it the most expensive one.

100+ hours and a production healthcare app later, I learned that for the model that writes your code[^1], price is a bad predictor of performance.

I ran 12+ models through the same harness on the same codebase. The differences were marginal. I spent €15 a month on tokens. That €15 wasn't an achievement — it was proof that the model was never the bottleneck.

External data backs this up:

- **[Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase)** on a multi-million-line codebase: token price is a poor predictor of actual task cost, and "open models are now able to handle even the highest level of task difficulty."
- **[Veracode's 2026 survey](https://www.veracode.com/resources/analyst-reports/2026-genai-code-security-report/)**: model size doesn't improve code security, and coding-specialized models aren't safer than general ones.

So what *does* differ between coding models, if not quality? Personality. DeepSeek-v4-Flash is thorough — it tests and checks its work, sometimes to the point of overthinking. GLM 5.2 is the opposite: concise and fast, but it takes shortcuts — I once asked it to test and verify something and it only ran greps, which gets you close but not all the way. Poolside Laguna M1 leans toward autonomy by default — it acts before asking, which is great when you want speed, costly when it goes wrong. This is fit, not capability. Try a few, pick by feel. Different people on your team may settle on different models, and that's fine.

Stop agonizing over model selection. Step out of the frontier bracket and try a couple of competent mid-range models — open-weight, last-gen frontier, whatever's accessible. Get a cloud subscription that gives you access to several, start from the affordable end, and go up until you're satisfied. You'll find one that works within the first day. Then move on. The model isn't where your time goes — and it shouldn't be where your attention goes either.

_Next in this series: the harness._


[^1]: Note that this is about the model that *generates the code changes* — the one in the coding phase. I experiment with stronger models for technical brainstorming and implementation planning; the coding agent consumes that plan.
