---
layout: post
title: "The EU's AI advantage isn't sovereignty. It's open source."
date: 2026-10-22
series: conversations
series_num: 2
series_title: Conversations
image: /assets/img/posts/open-source.svg
image_alt: "Open box with a dot in the middle"
---

This is a good time to notice that the narrative about LLM "alchemy in the hands of a few" is smoke and mirrors. In just over two weeks, five European teams shipped models across speech, image, and language — from midsize to ~1T parameters. Aleph Alpha released Kolibri-1: 78B MoE, 3.46B active per token, Apache 2.0 [^1]. Mistral put Large 4 into preview: ~1T parameters, 49B active, weights promised by month-end [^2]. Black Forest Labs shipped FLUX 3 [^3]. Three of five going open-weight. European labs are producing models that approach frontier level on many specialized domains at a fraction of the cost.

So if the models aren't differentiated, what are the big labs actually selling?

Separate the industry into two camps. The first controls the narrative and has the most to win or lose: OpenAI, Anthropic, Nvidia, Google, Microsoft, Amazon, Oracle. The second is everyone else — the long tail, the people who build on top. The long tail must not confuse the first group's manufactured hysteria with the actual distribution of value. The initial innovation — the paradigm jump — is available to everyone. What's being sold as unique is the surrounding platform, and the platform is where the lock-in lives. Claude Code, ChatGPT integrations, proprietary agent harnesses, curated plugin ecosystems. We'll have OpenAI worlds and Anthropic worlds, the same way we had AWS and GCP worlds.

This isn't EU vs US. It's big tech vs open source. And the open-source argument sounds like a 2010 hacker claim — until you realize that AI has changed the economics of building the alternative.

I lived through the cloud computing hype cycle. I spent my PhD years watching the EU start too late, accept the lock-in, and count its losses. In the 2010s, open source lost to cloud platforms because building the alternative was expensive. Distributed databases, identity layers, storage engines — that took teams of PhDs and years of engineering. Open source couldn't out-build the platforms.

The lock-in target this time is middleware — model routers, tool connectors, agent harnesses, integration glue. That's software. And AI writes software. The marginal cost of building the open-source alternative has collapsed. What took a platform team in 2015 takes a developer with a good harness in 2026. Open source doesn't need to out-build the platforms. It needs to out-organize them. That's a different fight, and it's winnable.

I ran 12+ models through the same open-source harness while building [Pflegebericht](https://app.pflegebericht.com), a production healthcare app. Open weight, European, American, Chinese. The differences were marginal. €15 on tokens per month. That €15 wasn't an achievement — it was proof the model was never the bottleneck. Databricks' benchmark on a multi-million-line codebase reached the same conclusion: "in many cases, simple harnesses like Pi performed best on our workloads" [^4]. The value is in the layer above the model — the harness, the tooling, the integration patterns. That's where the next battle is.

The protocols are being defined right now — MCP for agent-to-tool connections [^5], A2A for agent-to-agent [^6], AG-UI for agent-to-user [^7]. The CNCF's llm-d 1.0, released last week, is a Kubernetes-native distributed inference framework backed by Red Hat, IBM, Google Cloud, and NVIDIA [^8]. The Agentic AI Foundation, under the Linux Foundation, now hosts 10 projects — MCP, Agent Skills, Open Responses — uniting Anthropic, OpenAI, and Hugging Face around vendor-neutral governance [^9]. The pieces exist. The consolidation hasn't happened yet. Some are calling this the "Kubernetes moment" for open-weight AI [^10]. That's the right instinct — but Kubernetes took years to consolidate from competing orchestrators. The question is who drives that consolidation, and whether the open-source side organizes before the platforms capture the standards.

And here's the tell: the open-weight frontier is narrowing. Mistral's Voxtral line went closed after three Apache 2.0 generations [^11]. Mistral Large 4's weights are still "Coming soon" on Hugging Face, three weeks past the preview — and reports suggest the license may abandon Apache 2.0 for a $20M revenue gate, the same "free-until-you-succeed" model that Meta, DeepSeek, and Moonshot already adopted [^12]. Alibaba is reportedly planning a revenue share on the next Qwen [^13]. The labs know the models aren't the moat. The moat is the terms — and terms are a legal artifact, not a technical one. But the window where "open weight" meant "yours to build on" is closing, and the labs that shipped the open weights are learning the platform play from the same big-tech playbook we failed to answer last time.

This is where the EU comes in — not as a sovereignty argument, but as the actor with the motive, the talent, and the institutional weight to drive the open-source consolidation. The EU failed to build its own cloud platforms in the 2010s because it started too late and the build cost was prohibitive. Neither is true this time. The build cost has collapsed. The time is now. What's missing is focus and organization — and that's the real danger. Not capability. Not geopolitics. Focus.

China already learned this lesson; they'll spring ahead regardless. The real danger is having the wrong focus, or a lack of focus, or a lack of organization. We have the models, the talent, and the open-source ecosystem. The window is still open — but it's narrower than it was three weeks ago.

Two outcomes: (1) open source wins the middleware layer — shared, vendor-neutral control of the integration layer everyone depends on — or (2) the same platforms capture it, and we rent it back.

I hope 2027/2028 is closer to (1) than (2).

P.S.: And maybe we also need more real open-**source** models, and not just 'open-weight' "free-until-you-succeed" ones?

---

This is one of the more interesting observations I've had working through two hype cycles. If you've been working through similar questions — especially if you think middleware is the wrong level of abstraction, or I'm missing something — I'd be happy to compare notes.

[^1]: Aleph Alpha, [Kolibri-1 release](https://llm-releases.com/changelog), October 3, 2026. 78B open-weight MoE, 3.46B active per token, Apache 2.0, 1M context.

[^2]: Mistral Large 4, [public preview announcement](https://www.aninews.in/news/business/mistral-launches-1-trillion-parameter-large-4-model-plans-open-weight-release-by-month-end20261007084559), October 6, 2026. ~1T parameters, 49B active, MoE architecture. Weights and license still "Coming soon" on Hugging Face as of October 23, 2026. See also: [The License Countdown: Mistral Large 4 and the $20M Question](https://cryptorank.io/news/feed/c9fa6-the-license-countdown-mistral-large-4-and-the-20m-question).

[^3]: Black Forest Labs, [FLUX 3 release](https://aireiter.com/blog/flux-3-image-klein-review-tested), October 1, 2026. FLUX 3 Image Klein (5.6B) released October 15, 2026.

[^4]: Databricks, [Benchmarking Coding Agents on a Multi-Million-Line Codebase](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase). "The harness a model is called from dramatically impacts cost and quality. In many cases, simple harnesses like Pi performed best on our workloads."

[^5]: Model Context Protocol (MCP), donated by Anthropic to the Agentic AI Foundation, December 2025. See: [Anthropic donates Agent Skills to the Agentic AI Foundation](https://aiparabellum.com/anthropic-agent-skills-agentic-ai-foundation/), October 22, 2026.

[^6]: Agent2Agent (A2A) protocol, hosted at the Agentic AI Foundation under the Linux Foundation. See: [Agentic AI Foundation adds four projects to reach 10 in first year](https://www.unite.ai/agentic-ai-foundation-adds-four-projects-to-reach-10-in-first-year/), October 22, 2026.

[^8]: CNCF, [llm-d 1.0 release](https://sg.finance.yahoo.com/news/llm-d-1-0-advances-120000745.html), October 20, 2026. Founded by Red Hat, IBM, Google Cloud, CoreWeave, and NVIDIA. Now CNCF-governed.

[^9]: Agentic AI Foundation, [10 hosted projects announcement](https://www.unite.ai/agentic-ai-foundation-adds-four-projects-to-reach-10-in-first-year/), October 22, 2026. Co-founded December 2025 by Anthropic, Block, and OpenAI under the Linux Foundation. Hosts MCP, A2A, Agent Skills, Open Responses, OpenSandbox, OpenEnv, Agent Router, agentgateway, AGENTS.md, and goose.

[^10]: Tobi Knaup, [Open-weight AI is having its Kubernetes moment](https://tobi.knaup.me/2026-07-25-open-weight-ai-is-having-its-kubernetes-moment/), July 2026.

[^11]: Mistral Voxtral 3, [release notes](https://releasebot.io/updates/mistral), October 2026. Voxtral line went closed after three Apache 2.0 generations. See also: [Muhammad Ahmed blog](https://muhammad-ahmed.com/blog/), October 21, 2026.

[^12]: [The License Countdown: Mistral Large 4 and the $20M Question](https://cryptorank.io/news/feed/c9fa6-the-license-countdown-mistral-large-4-and-the-20m-question), October 23, 2026. Industry reports suggest Mistral may move from Apache 2.0 to a $20M monthly revenue-gate license, aligning with the "Club of Four" (StepFun, Meta, Moonshot AI, DeepSeek).

[^13]: Reuters, [Alibaba plans to charge big users of its next open-source AI model](https://www.reuters.com/business/retail-consumer/alibaba-plans-charge-big-users-its-next-open-source-ai-model-sources-say-2026-08-07/), August 7, 2026. See also: Reuters, [China's Moonshot in talks with Microsoft, Amazon, Google over K3 revenue sharing](https://www.reuters.com/business/retail-consumer/chinas-moonshot-talks-with-microsoft-amazon-google-over-k3-revenue-sharing-2026-08-26/), August 26, 2026. Moonshot's Kimi K3 license seeks revenue share of up to 30%.

