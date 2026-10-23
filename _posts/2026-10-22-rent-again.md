---
layout: post
title: "Rent, again."
date: 2026-10-22
series: conversations
series_num: 2
series_title: Conversations
image: /assets/img/posts/rent-again.svg
image_alt: "Open box with a dot in the middle"
---

The narrative about LLM "alchemy in the hands of a few" is smoke and mirrors. European labs just shipped frontier-approaching models across speech, image, and language in two weeks [^1]. So if the models aren't differentiated, what are the big labs actually selling?

That's easy — the oldest trick in the big-tech playbook: build a platform around the model and charge rent. Claude Code, ChatGPT integrations, proprietary agent harnesses, curated plugin ecosystems. We'll have OpenAI worlds and Anthropic worlds, the same way we had AWS and GCP worlds. The models are the commodity. The platform is the moat. The platform is where the lock-in lives.

This isn't EU vs US. It's big tech vs open source — again.

The 2010s cloud cycle ended with the long tail paying rent to a handful of platforms. Open source lost that cycle because building the alternative was expensive. Distributed databases, identity layers, storage engines — that took teams of PhDs and years of engineering. Open source couldn't out-build the platforms.

The lock-in target this time is middleware — model routers, tool connectors, agent harnesses, integration glue. The middleware is plumbing, not frontier research. The teams that learn how to make the best use of AI will build what a platform team built in 2015. The economics flipped. Open source doesn't need to out-build the platforms. It needs to out-organize them. That's a different fight, and it's winnable.

I ran 12+ models through the same open-source harness while building [Pflegebericht](https://app.pflegebericht.com/), a production healthcare app. Open weight, European, American, Chinese. The differences were marginal. €15/month on tokens total. That €15 wasn't an achievement — it was proof the model was never the bottleneck. Databricks' benchmark on a multi-million-line codebase reached the same conclusion: "in many cases, simple harnesses like Pi performed best on our workloads" [^2]. The value is in the layer above the model. That's where the fight is.

The protocols are being defined right now — MCP for agent-to-tool [^3], A2A for agent-to-agent [^4], AG-UI for agent-to-user [^5]. The Agentic AI Foundation, under the Linux Foundation, now hosts 10 projects — MCP, Agent Skills, Open Responses — uniting Anthropic, OpenAI, and Hugging Face around vendor-neutral governance [^7]. The pieces exist. The consolidation hasn't happened yet. Some are calling this the "Kubernetes moment" for open-weight AI [^8]. That's the right instinct — but Kubernetes took years to consolidate from competing orchestrators. The question is whether open source organizes before the platforms capture the standards.

And here's the tell: the open-weight frontier is narrowing. Mistral's Voxtral line went closed after three Apache 2.0 generations [^9]. Mistral Large 4's weights are still "Coming soon" on Hugging Face, three weeks past the preview — and reports suggest the license may abandon Apache 2.0 for a $20M revenue gate, the same "free-until-you-succeed" model Meta, DeepSeek, and Moonshot already adopted [^10]. Alibaba is reportedly planning a revenue share on the next Qwen [^11]. The labs know the models aren't the moat. The moat is the terms. And the terms are closing.

If producing LLMs isn't in the hands of the few — and it isn't — then the next frontier isn't open weight. It's open source. The whole pipeline — data, training, tooling, integration. That's where the effort goes. The window is open. It's narrower than it was three weeks ago.

---

*I've been through two hype cycles on this. I think the model isn't the moat and the economics just flipped. I might be an idealist — but defeatism isn't a counter-argument. If you've got a better one, bring it.*

## Footnotes

[^1]: In just over two weeks of October 2026: Aleph Alpha released Kolibri-1 (78B MoE, 3.46B active per token, Apache 2.0), [llm-releases.com](https://llm-releases.com/changelog), October 3, 2026. Mistral put Large 4 into preview (~1T parameters, 49B active, weights promised by month-end), [ANI](https://www.aninews.in/news/business/mistral-launches-1-trillion-parameter-large-4-model-plans-open-weight-release-by-month-end20261007084559), October 6, 2026. Black Forest Labs shipped FLUX 3, [aireiter.com](https://aireiter.com/blog/flux-3-image-klein-review-tested), October 1, 2026. Three of five going open-weight.

[^2]: Databricks, [Benchmarking Coding Agents on a Multi-Million-Line Codebase](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase). "The harness a model is called from dramatically impacts cost and quality. In many cases, simple harnesses like Pi performed best on our workloads."

[^3]: Model Context Protocol (MCP), donated by Anthropic to the Agentic AI Foundation, December 2025. See: [Anthropic donates Agent Skills to the Agentic AI Foundation](https://aiparabellum.com/anthropic-agent-skills-agentic-ai-foundation/), October 22, 2026.

[^4]: Agent2Agent (A2A) protocol, hosted at the Agentic AI Foundation under the Linux Foundation. See: [Agentic AI Foundation adds four projects to reach 10 in first year](https://www.unite.ai/agentic-ai-foundation-adds-four-projects-to-reach-10-in-first-year/), October 22, 2026.

[^5]: AG-UI Protocol, [GitHub repository](https://github.com/ag-ui-protocol/ag-ui), 2026.

[^7]: Agentic AI Foundation, [10 hosted projects announcement](https://www.unite.ai/agentic-ai-foundation-adds-four-projects-to-reach-10-in-first-year/), October 22, 2026. Co-founded December 2025 by Anthropic, Block, and OpenAI under the Linux Foundation. Hosts MCP, A2A, Agent Skills, Open Responses, OpenSandbox, OpenEnv, Agent Router, agentgateway, AGENTS.md, and goose.

[^8]: Tobi Knaup, [Open-weight AI is having its Kubernetes moment](https://tobi.knaup.me/2026-07-25-open-weight-ai-is-having-its-kubernetes-moment/), July 2026.

[^9]: Mistral Voxtral 3, [release notes](https://releasebot.io/updates/mistral), October 2026. Voxtral line went closed after three Apache 2.0 generations. See also: [Muhammad Ahmed blog](https://muhammad-ahmed.com/blog/), October 21, 2026.

[^10]: [The License Countdown: Mistral Large 4 and the $20M Question](https://cryptorank.io/news/feed/c9fa6-the-license-countdown-mistral-large-4-and-the-20m-question), October 23, 2026. Industry reports suggest Mistral may move from Apache 2.0 to a $20M monthly revenue-gate license, aligning with the "Club of Four" (StepFun, Meta, Moonshot AI, DeepSeek).

[^11]: Reuters, [Alibaba plans to charge big users of its next open-source AI model](https://www.reuters.com/business/retail-consumer/alibaba-plans-charge-big-users-its-next-open-source-ai-model-sources-say-2026-08-07/), August 7, 2026. See also: Reuters, [China's Moonshot in talks with Microsoft, Amazon, Google over K3 revenue sharing](https://www.reuters.com/business/retail-consumer/chinas-moonshot-talks-with-microsoft-amazon-google-over-k3-revenue-sharing-2026-08-26/), August 26, 2026. Moonshot's Kimi K3 license seeks revenue share of up to 30%.
