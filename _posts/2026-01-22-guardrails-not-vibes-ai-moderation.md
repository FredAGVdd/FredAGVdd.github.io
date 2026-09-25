---
layout: post
title:  "Guardrails, not vibes: shipping AI moderation"
date:   2026-01-22 18:40:00 +0200
categories:
- ai
- engineering
---

A community forum with real users is a wonderful thing right up until the spammers and the trolls find it. So over the last while I built and shipped an AI content-moderation system for exactly that situation, and I learned a few things worth writing down.

Lesson one: **don't put the model on the critical path for everything.** A deterministic denylist/regex gate sits in front, catches the obvious stuff instantly and cheaply, and only the genuinely ambiguous cases go to the model. Cheaper, faster, and far easier to reason about.

Lesson two: **tiers beat a boolean.** Block outright / hold for review / publish — three outcomes, not "yes/no". The "hold" bucket is where you keep your sanity.

Lesson three: **fail closed.** If the check errors, the content waits. Boring, correct.

And yes, the classic Scunthorpe problem is real — you need an allowlist or you'll be explaining to a nice person from Scunthorpe why they can't introduce themselves.

The model does the clever bit. The engineering around it does the *trustworthy* bit. Both matter.
