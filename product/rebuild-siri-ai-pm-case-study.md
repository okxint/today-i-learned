# How I'd Rebuild Siri From Scratch — An AI PM's Perspective

**March 24, 2026**

Apple just admitted defeat. They're paying Google $1B/year to run Siri on a custom Gemini model because their in-house LLM efforts couldn't ship anything competitive. I [wrote about the deal](../ai/apple-siri-gemini-relaunch.md) two weeks ago. But the more I think about it, the more I realize the real story isn't the partnership — it's the decade of product decisions that made it necessary.

So here's the exercise: if you handed me the Siri PM role on day one and said "rebuild this from scratch," what would I actually do? Not the hand-wavy "make it smarter" stuff. The actual product requirements, architecture decisions, and rollout strategy.

## First, the Autopsy: Why Siri Failed

Siri's problems weren't technical. They were organizational.

When Apple launched Siri in 2011, it was genuinely ahead. But Apple treated it like a feature, not a platform. The team was small, siloed, and — critically — had no authority to access data from other Apple services. The Maps team had their data. The Music team had theirs. Siri got to talk to each team through narrow APIs, like a contractor who needs permission to enter every room in a building they're supposed to be managing.

John Giannandrea (who Apple poached from Google in 2018 to fix exactly this) reportedly pushed for a unified data layer. He got partial buy-in. But Apple's privacy-first culture meant every data integration required a privacy review that could take months. Meanwhile, Google was feeding Assistant every search query, email, and calendar event on earth.

The Verge reported in 2024 that Siri's NLU (natural language understanding) stack was still largely rule-based — pattern matching with ML bolted on top. Not a foundation model. Not even close. By the time Apple started training its own LLMs seriously in 2024-2025, they were three years behind OpenAI and two behind Google.

The product failure was letting Siri become a voice interface to isolated features instead of an intelligent layer across the OS.

## The PRD I'd Write

Here's the product requirements document, stripped to what actually matters.

### Vision (one sentence)
Siri should be the system-level intelligence layer that understands your context, anticipates your needs, and takes action across every Apple surface — with zero data leaving Apple's ecosystem.

### Core User Problems
1. **"Siri can't do anything useful."** Users have been trained to only ask Siri for timers and weather. The failure rate on anything complex (multi-step requests, app-specific actions, contextual queries) is so high that users stopped trying years ago. This is the hardest problem — it's not just capability, it's trust recovery.

2. **"I have to repeat myself."** Siri has no memory. Every interaction starts from zero. Your assistant should know you take the 8:15 train, that "Mom" means the contact named Sarah, that when you say "the usual" at 7 AM you mean your coffee order.

3. **"It works on my phone but not on my Mac."** Siri's capabilities vary wildly across devices. The HomePod Siri is basically a different product from the iPhone Siri. Users don't think in devices. They think in tasks.

### Success Metrics (the ones that actually matter)

- **Task completion rate**: % of user requests that reach the intended outcome without fallback to manual input. Current Siri is estimated at ~50-60% for simple commands, sub-30% for multi-step. Target: 85% simple, 65% multi-step within 12 months.
- **Trust recovery rate**: % of users who try a complex Siri request after previously abandoning the feature. This is the metric that tells you whether you're actually winning back users, not just performing better on benchmarks.
- **Retry rate**: How often users have to rephrase or repeat. Every retry is a failure. Target: <10% retry rate on first-attempt requests.
- **Error recovery time**: When Siri fails, how quickly can the user get to the right outcome? A graceful failure ("I can't do that yet, but here's the screen where you can") is worth 10x more than a confused "I found this on the web."
- **Fallback-to-screen rate**: % of interactions where the user gives up on voice and taps instead. This should decrease over time. If it's increasing, you're losing.

Notice I didn't list "number of Siri interactions" as a success metric. That's a vanity metric. A user who asks Siri one thing and it works perfectly is worth more than a user who asks five things and three fail.

## The Architecture Decision: RAG vs Fine-Tuning vs Hybrid

This is where most AI PM discussions get hand-wavy. Let me be specific.

**The answer is a hybrid, but the ratio matters.**

The base model (whether it's in-house or licensed from Google) handles general language understanding, reasoning, and conversation. You fine-tune this on Apple-specific interaction patterns — the way people talk to voice assistants is different from how they type prompts. Shorter utterances, more ambiguity, more implicit context.

But you don't fine-tune on personal data. That's where RAG comes in.

The personal context layer should be a RAG system that indexes on-device: your contacts, calendar, recent apps, location history, purchase patterns, message threads (with consent). When you say "remind me about that thing John mentioned," the RAG layer retrieves the relevant message thread, and the base model uses it to construct the reminder.

Why not just fine-tune on personal data? Three reasons:
1. **Privacy** — fine-tuning bakes data into model weights, making it nearly impossible to delete. RAG keeps personal data in a retrievable index that users can inspect and delete.
2. **Freshness** — your calendar changes daily. Fine-tuning can't keep up. RAG indexes can update in real-time.
3. **Auditability** — when Siri does something with your personal data, you should be able to see exactly which data it accessed. RAG provides that trace. Fine-tuned models are black boxes.

The split I'd target: ~70% base model (general intelligence), ~20% RAG (personal context), ~10% fine-tuned behavioral layer (Apple-specific interaction patterns, safety tuning, device-specific adaptations).

## Error Rate Thresholds — The Part Everyone Skips

Here's the thing about probabilistic products that most PMs don't internalize: you can't ship at 95% accuracy and call it done. The 5% failure rate determines your entire brand perception.

For Siri specifically, I'd set asymmetric error thresholds:

- **High-stakes actions** (sending money, deleting files, sending messages to contacts): 99.5% accuracy required before shipping. One wrong Venmo payment and you've lost that user forever. If you can't hit this, add a confirmation step — the UX cost of "Send $50 to John?" is far lower than the trust cost of sending $50 to the wrong John.

- **Medium-stakes actions** (setting reminders, playing music, navigation): 95% accuracy threshold. Users will tolerate occasional misses here because the cost of failure is low and correction is easy.

- **Low-stakes / informational queries** (weather, sports scores, general knowledge): 90% is acceptable, with graceful degradation to web results. Nobody's going to rage-quit Siri because it got a trivia answer wrong.

The critical insight: **error rates should be measured per-user, not in aggregate.** If 99% of users have a great experience but 1% consistently hit failures (maybe they have an accent Siri handles poorly, or they use niche apps), your aggregate metrics look fine while those users are actively telling their friends Siri is garbage. Segment by user cohort and fix the tail.

## The Rollout Strategy

This is where Apple's Gemini deal actually makes strategic sense — if they're using it as a bridge, not a destination.

**Phase 1: Ship Gemini-powered Siri (now — iOS 26.4)**
Get the capability gap closed immediately. Users don't care whose model is running underneath. They care that Siri can finally hold a conversation and do multi-step tasks. Take Google's model, wrap it in Apple's privacy infrastructure, and ship it.

**Phase 2: Build the personal context layer (iOS 27)**
This is what Google can't replicate. While Gemini handles the general intelligence, build the on-device RAG system that makes Siri genuinely personal. This runs entirely on Apple silicon — no cloud dependency. Apple's M-series and A-series chips were basically designed for this workload. Use it.

**Phase 3: Gradually replace Gemini components with in-house models (iOS 27-28)**
Start with the easier parts — device control, app actions, system-level tasks where Apple has a natural data advantage. Keep Gemini for general knowledge and complex reasoning until Apple's own models are competitive. The user never notices the transition because the interface stays the same.

**Phase 4: Siri as platform (iOS 28+)**
Open the personal context layer to third-party developers — with user permission. Let Uber access your calendar to suggest rides before meetings. Let your grocery app know your dietary preferences. This is where the real moat gets built, because no other company has this combination of device-level access, user trust on privacy, and a billion-device installed base.

## The Organizational Change That Matters More Than the Tech

None of this works if Siri stays as a feature team. It needs to be an org-level priority with a single leader who has authority across all Apple services. The PM for Siri needs to be able to walk into the Maps team and say "I need real-time location context in the Siri index" and have that be a Maps team priority, not a favor.

Apple reportedly restructured exactly this way in late 2025, putting Giannandrea in charge of a unified "Apple Intelligence" org. If that's real and not just a reorg on paper, it's the most important thing Apple has done for Siri in a decade.

## My Take

The Gemini deal isn't a failure — it's the first smart Siri decision Apple has made in years. You don't win by building everything yourself. You win by shipping a great product and building strategic advantage over time.

But here's what would actually keep me up at night as the Siri PM: the trust deficit. Apple has spent 15 years training a billion users to believe Siri is dumb. You could ship the most capable assistant ever built and a huge percentage of your user base would never try it because they gave up in 2019. The product challenge is only half technical. The other half is a marketing and behavior-change problem that no model architecture can solve.

The PMs who succeed in AI aren't the ones who ship the best models. They're the ones who understand that probabilistic systems require a fundamentally different approach to quality — asymmetric error thresholds, per-cohort measurement, graceful degradation, and the humility to add a confirmation step instead of shipping a 96% accurate action that should require 99.5%.

That's the actual job.

*Sources: TechCrunch, The Verge, 9to5Mac, Apple Insider, Bloomberg, Fortune, MacRumors, Gadget Hacks*
