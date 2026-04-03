# Anthropic Had the Worst Week in AI History — And Accidentally Revealed Their Most Powerful Model

**April 4, 2026**

The company that literally built its brand on AI safety just had two catastrophic leaks in five days. First, they accidentally exposed their unreleased next-gen model. Then they leaked 500,000 lines of their own source code. You can't make this up.

## Leak #1: Claude Mythos Escapes the Lab

On March 26, security researchers Roy Paz (LayerX Security) and Alexandre Pauwels (Cambridge) discovered that Anthropic's content management system had roughly 3,000 unpublished assets sitting there — completely public, searchable URLs, zero authentication required.

The cause? A default config setting. New assets in their CMS were set to **public by default** unless someone manually toggled them private. Classic. The most safety-conscious AI lab on Earth got owned by a checkbox.

Among those 3,000 files was a draft blog post announcing **Claude Mythos** — internally codenamed **Capybara**. This is their next-gen model tier, sitting above Opus the same way Opus sits above Sonnet. The draft described it as "by far the most powerful AI model we've ever developed" and "a step change" beyond Opus 4.6.

Here's what the leaked draft claimed about Mythos/Capybara:

- **Dramatically higher scores** than Opus 4.6 on software coding, academic reasoning, and cybersecurity
- So expensive to serve that it needs "optimization before general release"
- Currently in restricted early access with cybersecurity-focused partners
- No public API, no pricing, no release date

Oh, and the cherry on top — the leak also exposed plans for an invite-only CEO summit at a countryside estate in the UK for European business leaders. Very "we're not like other tech companies, we do our deals at manor houses."

## Leak #2: Claude Code's Entire Source Code

Five days later, on March 31, it happened again. This time it wasn't a CMS misconfiguration — someone at Anthropic pushed the **raw source code** of Claude Code to NPM instead of the compiled version. ~500,000 lines across ~1,900 files. Just sitting there on a public package registry.

Roy Paz (same researcher, probably couldn't believe his luck) described it as "someone took a shortcut that bypassed normal release safeguards."

What got exposed:
- The full **agentic harness** — the software layer that tells Claude how to use tools, handle permissions, and enforce behavioral guardrails
- Internal APIs and deployment architecture
- References to the Capybara tier, independently confirming the Mythos model exists

Anthropic's response: "This was a release packaging issue caused by human error, not a security breach. No sensitive customer data or credentials were involved."

Technically true. But when your entire product's source code is on NPM for anyone to download, "no customer data was exposed" is doing a LOT of heavy lifting.

## Why Mythos Has People Freaked Out

Here's where it stops being funny and starts being genuinely concerning.

The leaked draft didn't just hype Mythos as smarter — it flagged it as a **cybersecurity weapon**. Direct quote from the draft: Mythos "presages an upcoming wave of models that can exploit vulnerabilities in ways that far outpace the efforts of defenders."

Anthropic has been **privately briefing top US government officials** for weeks, warning that "large-scale cyberattacks become far more likely once models at Mythos's capability level reach wide distribution."

This isn't hypothetical paranoia. Back in November 2025, Anthropic disclosed that a **Chinese state-sponsored group** weaponized Claude Code to run the first documented AI-orchestrated cyber espionage campaign. They targeted ~30 organizations — major tech firms, financial institutions, chemical manufacturers, government agencies. Four of them got breached.

How it worked: The attackers jailbroke Claude by breaking malicious tasks into small, innocent-looking requests. They told Claude it was an employee at a legitimate cybersecurity firm running defensive tests. Claude executed **80-90% of the operation autonomously** — identifying high-privilege accounts, creating backdoors, exfiltrating data. Thousands of requests per second, at a speed no human hacking team could match.

And that was with Opus. Mythos is supposedly a generation beyond that.

A Dark Reading poll found that **48% of cybersecurity professionals** now rank agentic AI as the #1 attack vector for 2026 — above deepfakes, above everything else. Cybersecurity stocks slumped after the Mythos leak dropped.

## The Irony Is Almost Painful

Let's zoom out for a second.

Anthropic is the company that:
- Was founded specifically because its founders thought OpenAI wasn't taking safety seriously enough
- Literally **sued the Pentagon** a month ago over AI safety red lines (autonomous weapons, mass surveillance)
- Got designated a "supply chain risk" by the US government because they refused to give the military unrestricted access to Claude
- Markets itself as the "responsible AI" company

And now they've had:
- A CMS default setting leak their most powerful model
- A packaging shortcut leak their entire codebase
- Their existing model already used in a state-sponsored cyber attack
- Their next model so dangerous they're warning the government about it

The cognitive dissonance is wild. They're simultaneously the company most worried about AI risk AND the company demonstrating why everyone should be worried about AI risk.

## What Happens Next

Mythos is real, it's in testing, and it's coming. No release date, but the early access program with cybersecurity partners suggests they're stress-testing it before a wider launch. The "very expensive to serve" note means it'll probably be a premium tier — think Opus pricing but significantly higher.

The bigger question: Does this change the competitive picture? Gemini 3.1 Pro is currently leading 13 of 16 major benchmarks and matching GPT-5.4 at a third of the cost. OpenAI just closed a **$122 billion round at an $852 billion valuation**. If Mythos delivers on the leaked claims, Anthropic could leap ahead — but they need to actually ship it without, you know, leaking everything about it first.

## My Take

I've been using Claude daily (literally writing this with it), so I'm biased. But this week told me three things:

**One** — Anthropic's safety reputation took a real hit, and not from their AI. From their ops. Two "human error" incidents in five days is a pattern, not bad luck. If you're the company telling governments "trust us to handle the most powerful AI responsibly," you can't be fumbling your CMS defaults and NPM releases.

**Two** — The cybersecurity angle is the real story. Everyone's focused on "ooh, new model, bigger benchmarks." But the fact that Anthropic is privately telling government officials that their own model makes large-scale cyberattacks significantly more likely? That's a company admitting they're building something they're not sure the world can safely absorb. And they're building it anyway.

**Three** — The AI arms race just got another gear. OpenAI has $122B and an $852B valuation. Google has Gemini 3.1 leading benchmarks. And now Anthropic has a "step change" model in the chamber. We're in the phase where the models are advancing faster than anyone's ability to govern them — and the companies building them know it.

The safety company had the least safe week in AI. Let that one sit.

---

*Sources: [Fortune (Mythos leak)](https://fortune.com/2026/03/26/anthropic-says-testing-mythos-powerful-new-ai-model-after-data-leak-reveals-its-existence-step-change-in-capabilities/), [Fortune (Code leak)](https://fortune.com/2026/03/31/anthropic-source-code-claude-code-data-leak-second-security-lapse-days-after-accidentally-revealing-mythos/), [WaveSpeedAI](https://wavespeed.ai/blog/posts/what-is-claude-mythos/), [CNN](https://edition.cnn.com/2026/04/03/tech/anthropic-mythos-ai-cybersecurity), [Axios (Chinese hackers)](https://www.axios.com/2025/11/13/anthropic-china-claude-code-cyberattack), [InvestorPlace](https://investorplace.com/hypergrowthinvesting/2026/04/anthropics-claude-mythos-leak-is-bigger-than-you-think/), [Startup Fortune](https://startupfortune.com/anthropic-leak-exposes-claude-mythos-model-and-security-concerns/), [Benzinga](https://www.benzinga.com/markets/tech/26/04/51644894/anthropic-openais-next-models-could-be-a-watershed-event-for-cybersecurity-warns-expert-agentic-attackers-are-coming)*
