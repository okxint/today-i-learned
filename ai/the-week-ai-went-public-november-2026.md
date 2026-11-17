# The Week AI Went Public: Anthropic's $1.4T IPO, Nvidia Without Jensen, and the Model Wars Nobody Saw Coming

**November 17, 2026**

This week is the one historians will point to when they write the chapter about AI moving from "tech sector curiosity" to "foundational financial infrastructure." Anthropic prices Wednesday, starts trading Thursday. Nvidia reports Q3 earnings Tuesday night for the first time without Jensen Huang on the call. And somewhere in the middle of all this, Alibaba quietly dropped a 2.4-trillion-parameter model that benchmarks suggest is a legitimately different beast from anything they've shipped before.

Let me try to make sense of it.

## Anthropic's IPO: The Numbers Are Absurd

The order book closed 6-7x oversubscribed. At the top of the $70-78 range, Anthropic would raise $64.35 billion — beating SpaceX's private record for a single raise — and begin trading at a $1.4 trillion market cap.

For reference: that's larger than Tesla. It's roughly 2x Meta. It's a company that did not exist six years ago, whose core product is a chatbot that competes with three other chatbots, and whose "moat" is a safety philosophy and a massive Amazon check.

Brad Gerstner at Altimeter put in for $5 billion — five times the largest IPO order he's ever placed. That number says more than any analyst note.

A few things worth unpacking here:

**The annualized revenue number is wild.** At $81 billion annualized, Anthropic is growing faster than AWS did at this stage. The enterprise bet — Claude embedded in workflows rather than used as a consumer chatbot — is apparently printing money. Every time a Fortune 500 company puts Claude inside their customer service stack, it's recurring revenue that doesn't require a marketing budget.

**The timing is cold-blooded.** They're pricing the same week Nvidia reports without Jensen, the same week the AI chip export control tightening dropped, the same week California sued OpenAI. Every headline that makes the AI sector look chaotic or risky actually helps Anthropic's "steady, safety-focused adult in the room" positioning. Dario Amodei did not miss this.

**The public market will change them.** This is the part I keep coming back to. Anthropic as a private company could optimize for "do the right thing by safety." Anthropic as a $1.4T public company has institutional shareholders who need a quarterly narrative. The "safety first" framing has been a fundraising and enterprise sales asset. As a public company, it has to be an earnings asset too. That tension doesn't have a clean resolution.

## Nvidia Earnings Without Jensen: The Vibe Is Different

Jensen Huang resigned November 11 after the Chinese spy story broke. Tuesday night, Nvidia is reporting Q3 for the first time with Colette Kress running the call.

The products are still the best in the world. Blackwell is sold out through 2027. Every major hyperscaler is locked into multi-year GPU procurement agreements. This quarter's numbers are going to be spectacular.

But the market is pricing in a leadership premium that's evaporating. Jensen didn't just run Nvidia — he *was* the narrative. The leather jacket, the datacenter-as-the-new-factory speech, the CUDA ecosystem as a 20-year moat story. He told that story better than anyone, and institutional investors bought the story as much as the chip.

Colette Kress is a CFO running a company that needs a visionary face. She's competent and credible. She is not Jensen. The stock is down ~12% from before the resignation. How it moves after earnings Tuesday tells you whether the market thinks this is a Jensen problem or a business problem.

My read: it's a Jensen problem. The business is structurally dominant in a way that one person's departure can't change. But "structurally dominant" and "stock goes up" aren't the same sentence anymore, because the multiple was priced on confidence in leadership continuity, not just on products.

## Qwen4-Max: 2.4 Trillion Parameters, $1.67 Average Task Cost

The timing is so good I keep checking if it's real: the same week Anthropic goes public at $1.4T, Alibaba ships a model that undercuts Claude's API pricing by 75%+ on output tokens.

Qwen4-Max is a Mixture of Experts architecture — 2.4 trillion total parameters, 71 billion active per token, native vision, 1 million token context. The benchmarks are genuinely interesting:

- Alibaba's Work360 benchmark (721 professional domains): Qwen4-Max at 52.69, up from Qwen3.8-Max at 47.74
- Agents' Last Exam v1.1: 46.7 (up from 27.9 on the previous version)
- Average cost per task on Work360: dropped from $4.43 to $1.67 — 62% reduction
- Terminal-Bench 4.0: 48.5 vs Opus 5.5's 59.6 (still behind frontier, but closing)

The legal agent benchmark is the interesting one: Qwen4-Max #1 at 21.3 on HLAB-Vals-1.1, versus Kimi K3.1 at 11.7 and Opus 5.5 at 9.2. That's not "competitive" — that's winning. In legal applications specifically. For a model that costs a fraction of Anthropic's enterprise pricing.

This is the China AI story in a nutshell. They can't yet match the absolute frontier on reasoning and coding benchmarks. But they're cost-engineering the gap into irrelevance for specific verticals. A law firm paying $4.43 per task for Claude vs. $1.67 per task for Qwen4-Max with better legal performance isn't a close call. That's a 62% budget line item.

## Gemini 4 Carbon: Google Does the Pricing Thing Again

Google dropped Gemini 4 Carbon quietly into this circus — $2 per million input tokens, $10 per million output, introductory pricing through November 30. After that it doubles.

This is Google's move: ship something competitive at a price that makes developers integrate it, then normalize pricing after the integrations are locked in. They've done this with every Gemini release. It works. Developers are price-sensitive at integration time and sticky afterward.

The "introductory pricing ends November 30" is doing a lot of work here. That's 13 days. Enough to get a production deployment hooked up, not enough to evaluate whether you should switch.

## Anthropic's Enterprise Play Is Actually Working

The Claude Meetings, Claude Sheets, Claude Whiteboards rollout this week is the enterprise moat in action. When Claude joins your Google Meet as a visible participant and starts on the work while people are still talking — that's a workflow integration that creates switching costs that have nothing to do with model quality.

This is what Anthropic figured out that the benchmark-obsessed discourse misses: enterprises don't switch AI vendors because a competing model scored 2% better on MMLU. They switch (or don't switch) because of integrations, security reviews, procurement relationships, and inertia. By getting into the actual meeting, the actual spreadsheet, the actual whiteboard, Anthropic is building a moat that doesn't depend on staying at the frontier. It just has to be good enough that the switching cost isn't worth it.

Microsoft is doing the same thing at their Ignite conference this week — new Azure architecture to cut the cost of running AI agents, deepening the enterprise AI infra lock-in. These are infrastructure plays, not model plays. The model is a commodity. The workflow integration is the moat.

## The Three Things This Week Actually Means

**1. The public market is now an AI frontier scorecard.** When ANT starts trading Thursday, every model release, every benchmark result, every capability announcement becomes a potential stock-moving event. That's a new dynamic that changes the incentives for every AI lab. Anthropic can no longer treat safety tradeoffs as internal philosophical debates — they're now disclosures.

**2. The China price gap is real and accelerating.** Qwen4-Max at $1.67 per task vs. Anthropic at $4.43+ is not a rounding error. It's a strategic threat to Anthropic's enterprise pricing power, specifically in the verticals (legal, finance, medical) where Chinese models are winning domain-specific benchmarks. The "US models are smarter" argument holds for some tasks. It doesn't hold for legal document review, apparently.

**3. Jensen's absence is a bigger deal than the market is pricing.** The stock is down ~12% but the analysis I'm seeing treats it like a typical CEO transition. It isn't. Jensen was the thesis. He was the reason the multiple was 35x revenue instead of 20x. When a company's story is the product — and Nvidia's story was Jensen's story — losing the storyteller is a business risk, not just a governance one. The board search will be the most important hiring decision in tech in years.

## My Take

The Anthropic IPO is the moment that will make everything before it look like pre-history. The first time a frontier AI lab goes public at $1.4 trillion, with real revenue, with institutional capital locked in and paying attention, it creates a ratchet. Everyone else has to either go public or raise at equivalent valuations to avoid looking like they're falling behind. OpenAI is next. xAI is next. Mistral is probably thinking about it.

The model that matters most this week isn't Claude or Gemini 4 Carbon. It's Qwen4-Max, specifically because it's winning legal benchmarks while costing 62% less. That's the template for how the frontier gets disrupted from below — not by being better overall, but by being better *enough* in specific, high-value domains where cost savings compound.

And Jensen. I keep coming back to Jensen. The leather jacket, the "data center is the new factory" framing, the CUDA moat narrative — he was running a chip company like it was a religion, and people bought in. What Colette Kress needs to do Tuesday night is give institutional investors a reason to believe the religion survives the high priest leaving. That's a harder pitch than it looks.

What a week. Genuinely one for the books.

*Sources: Yahoo Finance, CNBC, TradingKey, VentureBeat, MarkTechPost, Vals.ai, DataCamp, The Neuron, Rio Rundown, AI-Weekly, GuideGuru, RaceFans, ESPN F1*
