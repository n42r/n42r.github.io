---
layout: plain
---

# The model barely matters. The harness does.

When it comes to AI tooling, the harness matters more than the model. This is counterintuitive. Most teams obsess over model selection and treat the harness as plumbing. This is the lesson I learned after 50 hours, 13K lines of code on a production healthcare application, and 12+ models tested.

The **_agent harness_** is the most promising development to come out of the LLM space. The idea is dead simple. _Put the agent in a loop and allow it to call tools and execute commands on your computer._

Based on my experience and in external benchmarks, _**the harness moved outcomes more than the model**_:

- [Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase): same model, different harness, 2x cost difference, Pi (minimal) best
- [Composio's Comparison](https://composio.dev/content/best-ai-agent-harnesses): same model, 8 harnesses, 20-point spread, Oh My Pi best
- My experience: 12+ models, same harness ([Pi Agent](https://pi.dev/)), differences marginal with proper task scoping

The mechanism is context management. Databricks found that Pi sent roughly three times less context per turn than native harnesses like Claude Code or Codex. A simpler harness doesn't let the model wander; it keeps the working set tight, which means fewer tokens, fewer round-trips, and less noise competing with the actual task. The harness isn't just a UI preference. It's a context management decision, and context is the actual bottleneck.

Besides the numbers game, there is another reason why a simple (and modular) harness is better. A bare-bones harness forces you to adapt it to your environment. A feature-rich harness arrives with opinions about how you should work as well as constraints (such as which models to use). A minimal one arrives with tools and asks you to decide. That decision--how to configure the harness for your stack, team, codebase--is where the real adoption work happens. It's also where most teams skip the work and wonder why the results are mediocre. Databrick's aforementioned benchmark ends on a similar note:

> "At Databricks, we’ve always been wary of lock-in, not just to vendors, but to assumptions that make teams less flexible over time. [We] give engineers room to move across models and harnesses [...]"

There is more. **_A harness with feature creep can tend to create more problems than it solves_**. I once had a problem with agents that got stuck in infinite loops. So I spent some hours implementing an extension to detect them. In the next few days I wasted more time dealing with false positives caught by the extension (the solution became a problem). I eventually deleted it and started to stay in the room more and do less long-horizon tasks. The same can be said about many other "features" such as sub-agents, agent-orchestration, etc. 

Not only in extensions. I faced a similar experience with agentic skills. I installed around 30 skills, I found two to be helpful (used 5+ times successfully). I removed the rest, some of which deteriorated the performance.

Now the obvious question: what about the model? Do frontier models really make a difference for development tasks? Is bigger, or more expensive better?

- [Veracode's 2026 survey](https://www.veracode.com/resources/analyst-reports/2026-genai-code-security-report/): model size doesn't improve security, coding-specialized models aren't safer.
- [Databricks' Benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase): token price is a poor predictor of actual task cost. Open weight models are  able to handle the highest level of task difficulty.

The pattern is clear: model size and price don't predict outcomes for development tasks. Security doesn't improve with bigger models. Task completion doesn't require frontier models. What does predict outcomes is the environment around the model — the harness, the task scoping, and the documentation structure. I spent €15 on tokens across 12+ open-weight models and the differences were marginal. The €15 wasn't the achievement; it was the proof that the model was never the bottleneck.

The model barely matters. The harness does. And the simpler the harness, the better, because simplicity forces the discipline that actually drives results. 

When evaluating AI tooling, scrutinize the harness, not just the model. Start minimal. Add features only when they prove valuable. If you're spending more time managing your agent's guardrails than doing the work, the harness is too complex.

This is one architect's experience, validated by two independent benchmarks. Your mileage will vary, but the pattern is consistent enough to warrant testing.


---
### [Nasr Kasrin](https://kasrin.com/)

I help engineering teams evaluate and configure their AI-assisted development setup: from harness selection to task scoping to documentation architecture. If your team is deciding where to start, or wondering why current results don't match the hype, let's talk.

**[Contact](mailto:nasr.kasrin@gmail.com)** · **[CV](https://raw.githubusercontent.com/n42r/n42r.github.io/main/assets/pdf/resume_kasrin.pdf)**