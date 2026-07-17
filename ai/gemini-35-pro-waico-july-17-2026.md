# The day AI split in two: Gemini 3.5 Pro drops and 29 countries build a rival to the entire Western AI stack

**Date:** 2026-07-17
**Topic:** AI / Geopolitics

---

July 17 is the day you'll point to when someone asks when AI governance broke into two separate worlds.

In the space of 24 hours, Google launched Gemini 3.5 Pro — the most capable frontier model they've ever shipped — and 29 countries signed an agreement in Shanghai to create the World Artificial Intelligence Cooperation Organization, a China-led intergovernmental body designed to be the alternative to every AI governance framework the US and EU have been building for the last three years.

Both things happened today. On the same day. The irony is doing a lot of work.

## Gemini 3.5 Pro: what actually shipped

Google rebuilt this model from scratch. The original 3.5 Pro spec was scrapped, a full new pretraining run was done, and the result is:

- **2 million token context window** — double what Gemini 3.5 Flash offers, and roughly 10x what Claude Fable 5 ships with at ~200K tokens. This is the largest context window at frontier model quality, and it matters for real use cases: loading entire codebases, full document sets, multi-hour video transcripts
- **Deep Think reasoning mode** — a chain-of-thought reasoning layer similar to what OpenAI does with o3. Available on the $99.99/month Ultra tier
- **Pricing estimates**: $12–15 per million input tokens, $36–60 per million output tokens. Those are not cheap numbers. For context, Claude Sonnet 4.6 is $3 input / $15 output. Gemini is betting on quality per token, not cost per token

The rebuild is significant. Google didn't just tune the old model — they restarted. Whatever they saw in the original 3.5 Pro evals wasn't good enough, and they delayed by weeks to fix it. That the model is shipping at all is a statement; that it was rebuilt from scratch is more interesting.

The 2M context window is the lead feature and probably the real differentiator for enterprise. Most frontier model benchmarks converge within a few percentage points on standard tasks. Context windows don't. Running an 8-hour meeting transcript, a 10,000-file codebase, or 5 years of contract history through a model in a single call is a different capability class, not just a bigger number.

## WAICO: 29 countries, one very obvious subtext

The same day, Chinese Foreign Minister Wang Yi was in Shanghai for a signing ceremony that established the World Artificial Intelligence Cooperation Organization — 29 founding members, UN Secretary-General António Guterres in attendance, headquarters in Shanghai.

The founding member list reads like a who's-not-who of Western AI governance: Russia, Kazakhstan, Pakistan, Indonesia, Laos, and 23 others. The stated mission is "beneficial, safe, and fair" AI development. The unstated mission is obvious — China wants to set the governance rules for the global south before Washington and Brussels do.

Xi Jinping attended the World Artificial Intelligence Conference in Shanghai in person, the first time he's done that since the event began in 2018. That's not a scheduling coincidence.

This matters because AI governance isn't just about safety frameworks and model cards. It's about who sets the standards for AI in trade agreements, what "safe AI" means in procurement rules, which countries have to follow whose export controls, and who builds the infrastructure that 4 billion people in the global south end up using.

The US has the compute, the frontier models, and the best labs. China has the manufacturing supply chain, the state coordination capacity, and apparently 29 countries willing to sign an intergovernmental agreement at a conference where their president shows up personally. These are different kinds of leverage, and both of them are real.

## The Kimi K3 footnote

Also this week: Moonshot AI released Kimi K3, the first open model in the 3-trillion-parameter class. 2.8 trillion parameters, open weights. The largest open model that has ever existed.

Three months ago, open weights at this scale would have been unthinkable. Now it's a footnote in a week that includes Gemini 3.5 Pro and a new intergovernmental AI organization.

## My take

The Gemini 3.5 rebuild story is interesting for product reasons: Google saw a model that wasn't good enough and delayed rather than shipped. That's discipline you don't always associate with their AI launches (remember Gemini's debut in December 2023). If 3.5 Pro benchmarks well on the things that matter — coding, long-context retrieval, multi-step reasoning — it moves the frontier in a real way, not just a benchmark way.

The WAICO story is more consequential. The US strategy on AI has been: export controls on chips, Wassenaar Arrangement updates, bilateral agreements with allies, try to keep the frontier models out of adversary hands. China's counter-strategy, now formalized: build a competing governance bloc with enough countries that Western export controls become a strategic liability rather than a strategic advantage. If 29 countries are inside WAICO and treating Chinese AI infrastructure as the default, Nvidia's export controls become a story about which bloc your country is in.

The frontier model race and the governance race have been running in parallel for two years. Today's the first time they both peaked on the same calendar date.

Worth watching.

---

**Sources:**
- [Google Launches Gemini 3.5 Pro with 2-Million Token Context Window](https://inews.zoombangla.com/google-gemini-3-5-pro-launch-july-2026/)
- [Gemini 3.5 Pro: July 17 Launch After Google's Full Rebuild — Enterprise DNA](https://enterprisedna.co/resources/news/gemini-35-pro-july-17-rebuild-vs-deepseek-v4-2026/)
- [Gemini 3.5 Pro Targets July 17 — 2M Context, Deep Think, and the Unrestricted Frontier Model](https://aitoolsrecap.com/Blog/gemini-3-5-pro-july-17-launch-specs-pricing-2026)
- [29 Nations Join China-Led World AI Cooperation Organization — PYMNTS](https://www.pymnts.com/news/artificial-intelligence/2026/29-nations-join-china-led-world-ai-cooperation-organization/)
- [29 countries sign agreement on establishing WAICO — Xinhua](https://english.news.cn/20260716/2d364f232dd7456c8edf1d67d5125d37/c.html)
- [World Artificial Intelligence Cooperation Organization — Wikipedia](https://en.wikipedia.org/wiki/World_Artificial_Intelligence_Cooperation_Organization)
- [WAICO: Founding Details, Signatories, and Geopolitical Fallout — Studio Global AI](https://www.studioglobal.ai/discover/answers/search-fact-check-with-cited-sources-for-6a5999be7ecef4a300cf8e20)
