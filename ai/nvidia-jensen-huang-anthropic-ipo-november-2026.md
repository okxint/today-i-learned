# The Day AI Went Full Soap Opera: Jensen Huang Out, Anthropic Goes Public, and AMD Steals a Chip

**November 12, 2026**

I woke up this morning, opened my feed, and thought someone was pranking me. Jensen Huang — the man who *is* Nvidia, the guy who single-handedly turned a gaming chip company into the most valuable company on Earth, the dude in the leather jacket — resigned. Because of an affair. With an alleged Chinese spy. The same week Anthropic is pricing its IPO at $1.4 trillion.

This isn't a news day. This is a season finale.

## The Jensen Huang Story (And Yes, It's As Wild As It Sounds)

Let me give you the timeline, because it matters: a few days ago, Nvidia confirmed it had launched an "independent investigation" into Huang's personal relationships. This morning, the board accepted his resignation, effective immediately. CFO Colette Kress is now interim CEO while Nvidia runs a permanent search.

The reason? Huang had a romantic affair with Alice Huang — a Chinese tech executive who, per a New York Times report, had been recruited by China's Ministry of State Security to get close to him and extract intelligence about Nvidia's AI chip roadmap. He apparently didn't know. Or didn't ask. The NSA does not grade on that curve.

The stock opened down ~12%. For a company sitting at multi-trillion-dollar valuation, that's hundreds of billions of dollars wiped off in an hour. Jensen has been asked to testify before Congress. His leather jacket collection is probably unavailable for comment.

Here's the thing people are glossing over: this isn't just a corporate governance scandal. It's a national security event. Nvidia's H100/H200/B200 chip allocation is the single most geopolitically sensitive commercial asset on the planet right now. The export control fight between the US and China has been raging for years. And the man making the calls on what gets sold, to whom, may have been sleeping next to someone reporting back to Beijing.

That's a different category of problem than "CEO had an affair." That's the plot of a movie Nvidia did not want to star in.

Colette Kress is a solid operator — she's been CFO since 2013 and knows the finances inside out. But she's not Jensen. Nobody is Jensen. He co-founded the company in 1993, grew it through the gaming era, saw the AI wave coming years before the rest of the industry, and made the right call on CUDA when it mattered most. Finding a permanent successor for someone who built a religion around a chip company is not a two-week process.

Nvidia's products aren't going anywhere. The H200s still print money. The Blackwell architecture is still the only thing running frontier training at scale. But the market is now pricing in a year or more of leadership uncertainty at exactly the moment when every major competitor is trying to close the gap.

## Meanwhile: Anthropic Is Going Public

Seventeen blocks away from wherever Jensen is handling lawyers right now, Anthropic's IPO roadshow is apparently running so hot that the order book is already several times oversubscribed. The company is targeting a $1.4 trillion valuation — yes, that number is real — with 825 million shares priced between $70 and $78. Expected Nasdaq debut: November 19, under the ticker **ANT**.

For context: $1.4T would make Anthropic's public debut larger than SpaceX's private record raise. It's lower than the $2T peak estimate from early October, but still a number that would have sounded like fanfiction eighteen months ago.

Anthropic's whole pitch has always been "safety-focused AI" — which is either the most principled founding thesis in tech or the most effective fundraising hook in history, depending on your level of cynicism. The revenue is real, though. Claude is embedded in enterprises across the planet, the API is everywhere, and Amazon's bet of $4B+ in 2024 looks prescient in hindsight.

The timing is interesting too. This IPO isn't happening in an AI bull market — it's happening *during* one of the most turbulent weeks the AI industry has seen. If the book closes at $1.4T+ with the NVIDIA story dominating headlines, that's a signal the market is specifically bullish on Anthropic as a beneficiary of Nvidia's chaos, not just a victim of the noise.

There's a scenario where NVIDIA's leadership vacuum accelerates the race to build alternatives — AMD, Intel, Google's TPUs, Groq, Cerebras — and Anthropic is probably the best-positioned AI lab to diversify away from CUDA dependency. Which brings me to...

## Anthropic Already Started the AMD Run

Buried under the IPO headlines and the Jensen drama: Anthropic's Mythos team apparently ported Claude to run on AMD GPUs **in three days**. Three. Days.

CUDA moat measured. CUDA moat: smaller than advertised.

This matters enormously. The entire story of AI infrastructure for the last five years has been "you need Nvidia or you need Nvidia." Training happens on H100s. Inference happens on H100s. The alternative chips (AMD's MI300X, Google's TPUs, AWS Trainium) all exist, but porting a production model means months of CUDA kernel rewrites, debugging precision issues, losing performance, and crying.

Mythos did it in three days. The technical claim is that AMD's ROCm toolchain and HIP (which is basically "CUDA but for AMD") has matured to the point where a modern model architecture can be migrated without custom kernel work. If true — and Anthropic has zero incentive to lie about this in an IPO week — it means the CUDA moat just shrank from "competitive barrier" to "annoying weekend project."

Nvidia's stock was already down 12% from the Jensen news. Now add "their one defensible competitive advantage in inference is apparently a 3-day migration" to the thesis and see if it rebounds on fundamentals alone.

## The Actual Shape of Today

Three things just changed simultaneously:

**1. Nvidia's founder is gone under the worst possible circumstances.** This isn't a planned transition or a retirement after decades of success. It's an abrupt exit during a national security investigation. The company will survive and probably thrive — the product is too good and the demand is too structural — but every competitor just circled November 12, 2026 on their calendar as the day the pressure came off.

**2. Anthropic is about to have $64 billion in IPO proceeds and a public stock price.** That money doesn't go in a jar. It goes into compute, talent, and product. Dario Amodei has consistently played the long game — Constitutional AI, RSP, the safety narrative — but once you're public with a $1.4T cap and institutional shareholders, the long game and the quarterly earnings game start pulling in opposite directions. How they manage that tension will define the next five years.

**3. The CUDA monopoly just took a credibility hit.** One three-day AMD port doesn't end Nvidia's dominance. But it starts the narrative. And in tech, the narrative usually arrives 18 months before the numbers do.

## My Take

The Jensen story is going to get wilder before it gets calmer — Congressional testimony, more reporting from the Times, the discovery phase of whatever lawsuit is coming. But I keep coming back to what this means for the AI chip supply chain specifically.

The US export control fight with China has always had an Achilles heel: it's enforced at the chip level but Intel and Nvidia's executive ranks were never security-screened like defense contractors. Huang may genuinely not have known. That's arguably worse — it means the most critical dual-use technology company in the world didn't treat itself like a national security asset, because nobody made it. That changes now.

On Anthropic: the IPO is impressive, the timing is surreal, and I'm genuinely curious whether going public changes their research culture. The "safety first" framing has been a powerful differentiator with enterprises (especially after GPT-4 jailbreaks made every CISO nervous). But public company Claude has to show quarterly growth, justify that $1.4T cap, and compete with OpenAI, Google, and Meta all simultaneously. That's a lot harder than "build good AI with Amazon's money."

The AMD thing though? That's the detail I'd watch most closely. Nvidia's moat is compute. Specifically, it's the switching cost of CUDA — 20 years of ecosystem, libraries, and muscle memory. If that moat can be crossed in 72 hours by one motivated team at a competitor, then the story of "Nvidia wins AI forever" just got its first real footnote. Doesn't mean Nvidia loses. But it means the floor just moved.

Wild Wednesday. Genuinely wild.

*Sources: TechCrunch, CNN, CNBC, Fortune, Variety, SEC Form 8-K (Nvidia), Bloomberg, Al Jazeera, Yahoo Finance, Rio Rundown, Deep Gains*
