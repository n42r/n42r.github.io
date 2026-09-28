---
layout: post
title: "The toolbox reflex"
date: 2026-09-28
series: conversations
series_num: 1
series_title: Conversations
image: /assets/img/posts/toolbox-reflex.svg
image_alt: "Circular dot in a square in a square in a square."
---

 When one part of technical work becomes dramatically cheaper, the cost moves somewhere else. Our reflex is to reach for new tooling wherever it lands. Often, the right response is upstream, in process, or in simply stopping what created the problem.

AI-assisted development is the obvious example. If producing code becomes cheap[^1], the cost of reviewing, testing, and integrating that code jumps. Take the poster child: **code review**. GitHub's merged pull requests jumped from [around 25 million to 90 million per month](https://www.coderabbit.ai/blog/github-gives-maintainers-a-throttle-for-the-ai-pull-request). [Daniel Stenberg](https://daniel.haxx.se/blog/2025/07/14/death-by-a-thousand-slops/) shut down curl's bug bounty after the confirmation rate of reports fell below 5%. [tldraw](https://julien.danjou.info/blog/github-is-thinking-about-killing-pull-requests/) closed external pull requests. [Jazzband](https://thenewstack.io/ai-generated-code-crisis/) shut down entirely.

How did these projects respond? Not with tools. The responses were process changes: limits on pull requests, stronger accountability, different contribution policies, explicit human sign-off. The [Linux kernel](https://www.zdnet.com/article/linus-torvalds-and-maintainers-finalize-ai-policy-for-linux-kernel-developers/) responded with explicit rules around human review, responsibility, and transparency for AI-assisted contributions.

*This is where the toolbox reflex kicks in.* 

If review is where the cost landed, the obvious next move is: _build something that makes review cheaper._ 

Sometimes that's what we should do. But sometimes we're just moving the problem around. 

And right now, we're not only getting better at adopting existing tools — we're extraordinarily good at inventing new ones. A newly exposed cost can become the justification for an entirely new category of tooling before we've established whether the underlying problem deserves to exist. 

That doesn't make speculative tools useless. Some will turn out to be genuinely valuable. But it makes the reflex harder to notice.

## Where did the effort go?

I saw a different possibility while building Pflegebericht.

When I started the project, a typical session went: give the agent a task, it generates code quickly, then I'd spend the majority of my time in post-coding — testing, debugging, finding where the AI had *guessed* instead of asked. The auth workflow was typical: underspecified, quickly generated, then half the session gone to testing subtle combinations and user journeys that should have been decided before a single line was written.

The shift wasn't a new tool. A session now opens with "Welcome to the project" — the agent orients itself from the [documentation architecture](https://kasrin.com/blog/designing-for-amnesia/), and I hand it an issue. It explores the codebase, proposes approaches, and drills me with gaps and trade-offs. Most of my judgment happens here, not in the coding. When the approach is settled, I ask for an implementation plan. On harder tasks, I run a pre-mortem — *what would break months from now?* — and we close those gaps. Then the agent codes in minutes. I'd also stripped the harness down to one tool and two skills — the rest was overhead I'd built before I understood the problem. The coding step became boring. That's the point.

The distribution shifted from roughly 20% pre-coding to 60–70%. The effort didn't disappear. It moved upstream — into thinking, not tooling.

Where the effort goes won't always be upstream. Sometimes it's process, architecture, or simply stopping what created the problem. 

The skill isn't in the tooling. It's in _tracing where_ the cost moved — and _judging whether_ the right response is a tool, a process change, or nothing at all. 

Until you've done that, you haven't solved the original problem — you've just moved it.

---

This is one of the more interesting observations I've had working with AI. You may be experiencing something different. If you've been working through similar questions, I'd like to compare notes.

[^1]: We have to be critical and emphasize that this _still is a hypothesis_.
