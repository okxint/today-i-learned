# Anthropic is spending $4.5 billion a year on compute. That's why they're building their own chips.

**Date:** 2026-07-16
**Topic:** AI / Semiconductors / Business

---

Anthropic makes one of the best AI models in the world. They also have a compute bill that would make a CFO physically faint.

$4.5 billion annualized. About $375 million a month. Of that, 65% goes to AWS Trainium and EC2 clusters. Another 30% goes to Google Cloud TPUs. The remaining 5% is Nvidia H100s, mostly for research. So two of their closest distribution partners — Amazon and Google — are also their biggest infrastructure landlords. That's a dependency problem dressed up as a partnership.

The obvious fix is what every big tech company eventually figures out: build your own silicon.

This month, Anthropic confirmed they're in early talks with Samsung to manufacture a custom inference chip on a 2nm process. They also quietly hired Clive Chan, one of the early members of OpenAI's silicon team, to help design it. Samsung, conveniently, was already a strategic investor in Anthropic's $65 billion fundraising round. Vertical integration starts with relationships.

## The math that makes custom silicon inevitable

When you're spending $375M a month on compute, even a 20% efficiency gain is worth $900M a year. That's enough to fund a serious chip program multiple times over.

The problem with buying compute from AWS or Google is that you're optimized for their workloads, not yours. AWS Trainium was designed for general inference at scale. Google TPUs were designed around TensorFlow and then adapted for everything else. Anthropic's inference patterns — long context windows, extended thinking, multi-turn agent sessions — have specific characteristics that a general-purpose accelerator isn't going to nail perfectly.

OpenAI figured this out faster. They've already announced "Jalapeño," a custom inference chip built in partnership with Broadcom. Better performance-per-watt than off-the-shelf alternatives. Google has TPUs. Amazon has Trainium and Inferentia. Microsoft has Azure Maia. Now Anthropic is the last major AI lab without a chip story, and that gap is starting to matter.

## Why Samsung and not TSMC

TSMC is the obvious choice for anyone building advanced chips. But TSMC is also the most overbooked semiconductor fab in history right now — June 2026 revenue was up 68% year-on-year, N3 capacity is sold out through year-end, and every hyperscaler on the planet is fighting over the same Nvidia allocations.

Samsung's 2nm process is legitimately competitive. It's not TSMC's N2, but the gap has been closing. More importantly, Samsung has capacity, a strategic investment relationship with Anthropic, and strong motivation to prove their foundry business can compete. For a chip that's still in early-stage design discussions, Samsung is the pragmatic call.

## What this actually means

The shift from "AI lab" to "vertically integrated AI infrastructure company" is accelerating across the industry. Training a frontier model requires billions in GPU clusters. Serving it at scale requires optimized inference hardware. Managing the supply chain requires your own silicon. Nobody planned for AI companies to end up looking like this, but here we are.

The irony is rich: Anthropic spent years distinguishing itself by being the "safe" AI lab that wasn't obsessed with moving fast. And now they're chasing down Samsung to build custom 2nm processors. The business of AI infrastructure is humbling to everyone eventually.

Samsung's foundry reputation also gets a boost if this lands. After years of struggling to compete with TSMC for premium customers, landing Anthropic — even at an early stage — is a credibility win. SK Hynix just raised $26.5B on Nasdaq in the largest ADR offering in financial history. South Korean semiconductor companies are having a moment.

## My take

Custom silicon is not a guarantee of anything. Google has had TPUs for a decade and still uses Nvidia for plenty of workloads. Apple spent years building the M-series chip and it's genuinely excellent — but it took a while to get there. Anthropic is at the "early talks" stage, which in chip timelines means they're probably 3-4 years from production silicon.

What it signals, though, is that the AI compute market is maturing fast. When every major lab is racing to own their inference stack, the era of "just rent GPUs from AWS" is ending for frontier AI. The economics push you toward vertical integration once you hit a certain scale. Anthropic hit that scale.

The $4.5 billion compute bill is not a problem Anthropic can conference-call their way out of. They need a chip. Samsung needs a high-profile 2nm customer. This deal makes sense from both sides.

Whether it ships on time, on budget, and with the performance gains they need — that's a different article for 2029.

---

**Sources:**
- [TechCrunch - Anthropic is discussing a new custom chip with Samsung](https://techcrunch.com/2026/07/02/anthropic-is-discussing-a-new-custom-chip-with-samsung/)
- [Bloomberg - Anthropic in Talks With Samsung for Custom AI Chip](https://www.bloomberg.com/news/articles/2026-07-02/anthropic-in-talks-with-samsung-for-custom-ai-chip-information-mr3l34t4)
- [Lambda Finance - Anthropic Compute Costs: 4.5 Billion Annualized](https://www.lambdafin.com/articles/anthropic-compute-costs)
- [FourWeekMBA - Anthropic Courts Samsung to Build a Custom Claude Inference Chip](https://fourweekmba.com/ai-anthropic-samsung-custom-claude-inference-chip/)
- [AI Weekly - Anthropic in Early Talks With Samsung to Make Custom AI Chip](https://aiweekly.co/alerts/anthropic-in-early-talks-with-samsung-to-make-custom-ai-chip)
- [TechTimes - Anthropic in Talks With Samsung to Build Custom AI Chip, Aiming at 2nm Process](https://www.techtimes.com/articles/319574/20260702/anthropic-talks-samsung-build-custom-ai-chip-aiming-2nm-process.htm)
- [BuildFastWithAI - AI News Today July 14 2026](https://www.buildfastwithai.com/blogs/ai-news-today-july-14-2026)
