---
layout: plain
title: The model barely matters. The harness does.
date: 2026-08-30
---

# The model barely matters. The harness does.

I started with 6 harnesses, 20 skills, and 8 plugins. I ended with one harness, two skills, and a working production app. When it comes to AI tooling, the harness matters more than the model — most teams obsess over model selection and treat the harness as plumbing. That's what 50 hours, 13K lines of code on a production healthcare application, and 12+ models tested taught me.

The **_agent harness_** is the most promising development to come out of the LLM space. The idea is dead simple. _Put the agent in a loop and allow it to call tools and execute commands on your computer._

Based on my experience and in external benchmarks, _**the harness moved outcomes more than the model**_:

- [Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase): same model, different harness, 2x cost difference, Pi (minimal) best
- [Composio's Comparison](https://composio.dev/content/best-ai-agent-harnesses): same model, 8 harnesses, 20-point spread, Oh My Pi best
- My experience: 12+ models, same harness ([Pi Agent](https://pi.dev/)), differences marginal with proper task scoping

The mechanism is context management. Databricks found that Pi sent roughly three times less context per turn than native harnesses like Claude Code or Codex. A simpler harness doesn't let the model wander; it keeps the working set tight, which means fewer tokens, fewer round-trips, and less noise competing with the actual task. The harness isn't just a UI preference. It's a context management decision, and context is the actual bottleneck.

Think of the difference between a terminal and a GUI application. The terminal gives you all the operations; you decide which to use, chain, and build scripts around. The GUI restricts you to workflows someone else built. I started with a one-shot harness that gave me two dials: a text field and a submit button. No visibility into what was running, no control over what to add or remove. A minimal harness like Pi flips that — you get tools and you decide how to configure them for your stack, team, and codebase. That decision is where the real adoption work happens. It's also where most teams skip the work and wonder why results are mediocre. Databricks' benchmark ends on a similar note:

> "At Databricks, we’ve always been wary of lock-in, not just to vendors, but to assumptions that make teams less flexible over time. [We] give engineers room to move across models and harnesses [...]"

There is more. _An extra feature in the harness can create more problems than it solves_. I once had a problem with agents that got stuck in infinite loops. So I spent some hours implementing an extension to detect them. In the next few days I wasted more time dealing with false positives caught by the extension (the solution became a problem). I eventually deleted it and started to stay in the room more and do less long-horizon tasks. That automatically solved another--deeper problem--human attention and oversight. The landscape of agentic AI is still in its infancy and moving fast, so starting with fancier features tends more so than not to become a hindrance.

Not only in extensions. I faced a similar experience with agentic skills. I installed around 30 skills, I found two to be helpful (`gdpr-compliant` and `pre-mortem`). I removed the rest, some of which deteriorated the performance.

Now the obvious question: what about the model? Do frontier models really make a difference for development tasks? Is bigger, or more expensive better?

- [Veracode's 2026 survey](https://www.veracode.com/resources/analyst-reports/2026-genai-code-security-report/): model size doesn't improve security, coding-specialized models aren't safer.
- [Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase): token price is a poor predictor of actual task cost. Open weight models are  able to handle the highest level of task difficulty.

The pattern is clear: model size and price don't predict outcomes for development tasks. Security doesn't improve with bigger models. Task completion doesn't require frontier models. What does predict outcomes is the environment around the model--the harness, the task scoping, and the documentation structure (a subject for another day). I spent €15 on tokens across 12+ open-weight models and the differences were marginal. The €15 wasn't the achievement; it was the proof that the model was never the bottleneck.

The model barely matters. The harness does. And the simpler the harness, the better, because simplicity forces the discipline that actually drives results. 

This is one architect's experience, validated by independent benchmarks. When evaluating AI tooling, scrutinize the harness, not just the model. Start minimal. Add only what proves valuable.

<br />

---

<br />

*If your team is evaluating AI coding tools, harness selection is where most of the outcome is decided.*

<br />

## [Nasr Kasrin](https://kasrin.com/)

I help engineering teams adopt AI-assisted development — from tooling 
setup to architecture conventions to team workflows. 15 years of 
solution architecture, now focused on what changes when AI writes 
most of the code.

**[Get in touch](mailto:nasr.kasrin@gmail.com)** · **[More writing](https://kasrin.com/blog)** · **[LinkedIn](https://linkedin.com/in/nkasrin)**