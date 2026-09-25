---
layout: post
title:  "Sending in the clones: multi-agent workflows"
date:   2026-04-15 08:05:00 +0200
categories:
- ai
- engineering
---

The single-assistant-in-a-chat-window thing is fine for small stuff. But the moment a job is *broad* — "find every place we do X", "review this change from five angles" — one agent plodding through it sequentially is the wrong shape.

Lately I've been building **multi-agent workflows**: fan the work out across a handful of subagents, each with a narrow brief, then gather and reconcile. One scouts, several implement in parallel, and — my favourite — a couple play adversary and try to *refute* the proposed change before it's allowed to live. Majority-refutes-it-dies is a shockingly good filter for plausible nonsense.

Two things make or break it:
1. **Decompose well.** Bad fan-out just multiplies confusion. Good fan-out gives each agent something it can finish without the others.
2. **Verify, don't trust.** The adversarial pass is not optional. AI output that nobody challenged is a liability wearing a nice suit.

Wall-clock drops, coverage goes up, and the quality bar actually rises because disagreement is built in. It feels less like "using AI" and more like running a tiny, fast, slightly argumentative team.
