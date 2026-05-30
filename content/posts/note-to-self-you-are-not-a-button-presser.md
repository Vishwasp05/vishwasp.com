---
title: "Note to Self: You Are Not a Button Presser"
date: 2026-05-30
description: "A fresh grad's observations on AI coding tools: comprehension fatigue, deadline pressure, loss of context, and tunnel-vision debugging — and what to do about it."
---

> *PSA: This is a rant-cum-whatToDo post. Please skip if you're not into that! Have a great day.*
>
> *One tip for ADHD that I came across is to deliberately make unpolished work and push it to escape the perfection paralysis. Will return to this regularly to refine and articulate better. Thanks for understanding.*

---

Unless you've been living under a rock, you've been asked to use AI to 10000x your output. It has become a cliché at this point for someone to just randomly say, "Just use AI, bro." And there's no doubt about it being fairly useful. It really is - however, I feel we (at least I) make it more than it is, and the mismatched expectations give birth to unnecessary friction that benefits no one.

I'm writing this from the perspective of a fresh graduate. A little background: I've ~1.5 YoE interning at startups of different scales - not your run-of-the-mill prototypes, but actual code shipped to prod. I've pushed close to 100k LoC at Temple. There are certain observations I've made about my usage of AI; some patterns have emerged, which I'll talk about here, and how I'm trying to circumvent them.

---

## The Four Patterns

1. **Comprehension Fatigue**
2. **Tug of War with Deadlines**
3. **Loss of Context**
4. **Tunnel of Bug**

---

## 1. Comprehension Fatigue

This is going to sound counterintuitive since it's my job, as a software engineer, to read and write code for a living - but when interacting with coding tools, it becomes tiring quickly to read the insane amount of, dare I say, confident garbage. Going back and forth. It's tiring. *"No, I meant this." "Get a grip, smartypants, I never told you to make this change"* - and it's a constant struggle to get it to do something.

It's partly a communication gap problem, but isn't that how natural language works? With certain assumptions. It's not C code where `int` can only be `int`. Natural language, whether you like it or not, is to some degree always ambiguous. That ambiguity quickly piles up, and gosh, does it drain the life out of me.

You'd argue: *"Just add this in the `instructions.md`: 'You're a senior engineer who speaks to the point.'"* And I'd agree - but when you're burning through a week's worth of usage in a day, that small error in communication piles up quickly.

Didn't we collectively as a field spend the last 80-odd years coming up with a formal language to remove this specific ambiguity? Sure, it's one level up, but it's there nonetheless, and now we want to reintroduce it?

> *"Unlike a formal algorithm - defined by a clear, unambiguous list of instructions - natural language can be interpreted in multiple ways. As anyone with programming experience knows, ambiguous requirements often necessitate an iterative process of refinement: a provisional solution is provided, the user tests it, and subsequent adjustments are made until the final, correct implementation is achieved."*
> — [arxiv.org/pdf/2505.02952](https://arxiv.org/pdf/2505.02952)

---

## 2. Tug of War with Deadlines

7/10 times, I don't even read the full response of the model and just hit **Okay | Allow** to quickly build the app I'm working on to see if what I was trying to solve is achieved or not. This quickly spirals into a fragile, oopsie-daisy mess of code that "just works," but I've no idea how or why.

This, coupled with tight deadlines, gives me a false sense of progress where, at best, I've come up with a working happy-path implementation and, at worst, something that works under very strict conditions and fails under every other - which is promptly made aware to me when someone outside my context window runs the feature.

So not only have I produced fragile garbage, I've used up time I could've spent using a pen and paper to work out the solution. Unfortunately for me, pen-paper rubber ducky talk doesn't burn any tokens.

---

## 3. Loss of Context

When Claude Code or Codex works across multiple files, and under the tight pressure of delivering a feature *now* - half my team is gone, surprise, but the workload isn't - it has become very common for me to lose context of the changes made. I micro-focus on whether the feature is working or not.

This doesn't become apparent until my PR is in review and a reviewer sitting next to me asks a question to which I'm dumbfounded. I've lost count of the occasions where I've had to say, while my PR is open: *"Please let me check what and where this change was made and how/why it was added."*

Losing context is basically walking the walk of shame. *Wdym I don't know why/where this change came from?*

---

## 4. Tunnel of Bug

When solving a bug, I rarely get the time to jump through files and traceback an issue, and my debugging process looks like:

> *"Hey Claude, this is the issue, breaking under these conditions, pls fix."*

I know - not the most optimal. However, I do want to highlight that Claude or any AI tool, for that matter, gives up the larger context in favour of solving the issue at hand. It tunnel-visions into that bug and ignores what ripple waves it may create.

This is especially hard to verify as a fresh graduate, as I'm still developing my eye for detail. I may zone in on just the issue and not the surrounding context, which may only surface in a PR review - or worse, present itself as an issue to the user, which for any consumer product is catastrophic.

---

## What to Do?

Well, I'm now taking my sweet, sweet time to write a full project from scratch, with only Google as my aid. It's been very tempting to convince myself that it's okay to use some AI tool as a pure typist, but I'm fighting that urge every day.

I think these tools can better support me when my hands are already dirty. Remember, kids (telling this to myself): **"Trust but verify"** - and right now I need to build that verification pipeline so that Claude/Codex don't take me for a ride, sounding confident.

My goal for this project, spanning over 30 days, is to be more fluent in:

- Reading documentation
- Figuring out obscure APIs and creatively using them
- Reasoning through decisions with myself and during PR reviews
- Leaving meaningful comments and helping maintain a healthy codebase

Comprehension is the biggest one on my list. Being able to read through a lot is a necessary skill, a little bird tells me.

---

## How?

I'm building an **image rendering engine** - which doesn't necessitate a backend (something I've used as an excuse in the past). It will let me touch rarely-touched APIs like Metal and some C++, introduce core CS concepts, and get into concurrency and tight memory constraints, so that when I stress test the app it doesn't crash.

The goal is to start building that intuition where I focus on not only micro but also macro. A rendering engine is a good example of something I can't reuse already-learned patterns for, breaking me out to actually research things. It's also notorious for tight constraints - in an effort to train (or at least expose) myself to building something that's not just *"it works on my machine"*, but performant code that takes the broader system into consideration.

I hope to write a devlog regularly with any learnings I may have.

If you have suggestions, tips, or recommendations for the above problems, feel free to write to me.

---

*Goodbye*
