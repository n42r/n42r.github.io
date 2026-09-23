---
layout: post
title: "The toolbox reflex"
date: 2026-09-23
series: conversations
series_num: 1
series_title: Conversations
image: /assets/img/posts/toolbox-reflex.svg
image_alt: "Square in a square in a square."
---

We make one category of technical work cheaper, and then reach for new tooling to solve the bottlenecks that appear downstream.

Sometimes that's the right thing to do.

I'm starting to think we reach for it too quickly.

I've done this myself.

My agent kept falling into infinite loops, so I built a guardrail extension to stop it. It worked. Then I discovered I was spending more time managing the guardrail's false positives than the original problem had cost me. The solution had become the problem.

I removed it.

Shorter tasks and more human intervention made the problem disappear. 

The pattern repeated.

When I started experimenting with agent harnesses, I installed six of them, with twenty skills and eight plugins — armed for a battle I didn't understand yet. I eventually ended up with one minimal [harness](https://pi.dev/) and two skills. [Databricks' benchmark](https://www.databricks.com/blog/benchmarking-coding-agents-databricks-multi-million-line-codebase) on a multi-million-line codebase found the same thing: "simple harnesses performed best on our workloads."

More features hadn't made the system better. Stripping it down had.

Then there was the schema.

One line of change to a domain contract stalled an entire pipeline. The agent spiralled into TypeScript dependency hell, rewriting contracts to make the types pass. I pulled the plug and tried a frontier model at roughly fifty times the cost.

It produced fancier-looking hallucinations.

I closed both agents, took out pen and paper, and solved it by hand.

## When the bottleneck moves

I think there is a broader pattern here.

When one part of a technical process becomes dramatically cheaper, the bottleneck often moves somewhere else.

AI-assisted development is the obvious example. If producing code becomes cheap, the cost of understanding, reviewing, testing and integrating that code becomes relatively more important. GitHub's merged pull requests jumped from [around 25 million to 90 million per month](https://www.coderabbit.ai/blog/github-gives-maintainers-a-throttle-for-the-ai-pull-request). [Daniel Stenberg](https://daniel.haxx.se/blog/2025/07/14/death-by-a-thousand-slops/) shut down curl's bug bounty after the confirmation rate of reports fell below 5%. [tldraw](https://julien.danjou.info/blog/github-is-thinking-about-killing-pull-requests/) closed external pull requests. [Jazzband](https://thenewstack.io/ai-generated-code-crisis/) shut down entirely.

The interesting part is how these projects responded.

The responses included process changes: limits on pull requests, stronger accountability, different contribution policies, explicit human sign-off. The [Linux kernel](https://www.zdnet.com/article/linus-torvalds-and-maintainers-finalize-ai-policy-for-linux-kernel-developers/), for example, responded with explicit rules around human review, responsibility and transparency for AI-assisted contributions.

[The cost to create has dropped. The cost to review hasn't.](https://github.com/orgs/community/discussions/197319)

*This is where the toolbox reflex kicks in.*

If review becomes the bottleneck, the obvious next move is to build something that makes review cheaper.

Sometimes that's what we should do.

But sometimes we're just moving the problem around.

And in the current environment, there is another force at work. We're not only getting better at adopting existing tools. We're getting extraordinarily good at inventing new ones.

When software is cheap to build, a newly exposed bottleneck can quickly become the justification for an entirely new category of tooling. Someone can identify the problem, build a prototype, add an integration layer, and turn it into a product before we've really established whether the underlying problem deserves to exist.

That doesn't make the resulting technology useless. Some of those categories will turn out to be genuinely valuable.

But it makes the reflex harder to notice.

The technology is no longer just waiting for us on the shelf. We can manufacture the shelf while we're still deciding what we need.

## Where did the effort go?

I saw a different possibility while building Pflegebericht.

When I started the project, a typical development session roughly looked like this:

**20% pre-coding → 30% coding → 50% post-coding**

A lot of the human effort came after the code existed: debugging, correcting, tuning and figuring out what the AI had misunderstood.

As I developed a more deliberate AI-assisted workflow, that distribution changed substantially:

**60–70% pre-coding → ~20% coding → 10–20% post-coding**

I spent much more time establishing the problem, constraints, domain contracts, architecture, context and intended approach before asking the AI to make a single change.

The coding itself became a smaller part of the process.

And the surprising part was that this didn't feel like slowing development down. It reduced the amount of expensive human attention spent cleaning up after the implementation.

I'm not suggesting that 60–70% pre-coding is some universal optimum.

The interesting observation is that when implementation became cheap, the effort didn't disappear.

*It moved.*

In my case, it moved upstream.

Instead of:

**generate → inspect → discover misunderstanding → fix → repeat**

The process looked like this:

**understand → brainstorm approaches → decide → plan implementation → generate → verify**

I also used AI in several of these steps, including to support technical analysis and oversight.

Most of my judgment moved into the phases before code generation.

But that's only one possible destination for the effort.

Sometimes the answer will be more human attention. Sometimes it will be more conventional engineering. Sometimes it will be a process change, an architectural change, a different allocation of responsibility, or simply stopping the thing that created the problem.

The important part is to notice where the effort went before deciding what to do about it.

## Who carries the consequences?

There is another reason I think this deserves more attention in established organizations.

The person building a tool and the organization adopting it don't necessarily carry the same costs.

A new tool can be exciting for its creator. For the adopter, it may also mean integration, training, maintenance, process changes, new dependencies, vendor lock-in and a new class of failures that someone has to own.

A two-person startup can install something on Monday and throw it away on Friday.

An established organization may still be carrying the consequences years later.

That doesn't mean established organizations should avoid new technology. It means the calculation is different.

When the market is moving quickly and everyone is being told that a new category of technology will change how we work, I think it is worth asking a slightly unfashionable question:

**What happened to the problem we were trying to solve?**

Did it actually disappear?

Did the cost move somewhere else?

Did we create a different problem in the process?

And does that new problem actually need another category of tooling?

---

This is one of the more interesting observations I've had working with AI. You may be experiencing something different, or learning very different lessons.

Over the next few weeks, I'm talking to engineers, architects, technical leaders and founders about where AI is genuinely creating leverage in their work, where it's mostly adding complexity, and how the role of technical leaders is changing as AI takes on more of the implementation. I'm not looking for agreement — I'm looking for the observations that don't match mine.

I'll publish a synthesis of what I hear — the patterns, disagreements and surprises.

It's also how I'm exploring my consulting practice: understanding real problems before deciding too narrowly what the answer should be.

If you've been working through similar questions, I'd like to compare notes.
