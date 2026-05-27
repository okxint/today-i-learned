# The AI PM Gap: What Most Product Managers Still Don't Understand About Building with LLMs

**May 27, 2026**

Companies are racing to hire "AI PMs." Most job descriptions are a copy-paste of regular PM requirements with "experience with LLMs" tacked on at the end. The candidates applying for these roles are mostly regular PMs who have used ChatGPT and added a line to their resume. And the products coming out of these teams — predictably — are not good.

Here's what most product managers still don't understand about building with language models.

---

## The evaluation problem is actually a product problem

Traditional PM runs experiments. You ship a feature, you A/B test it, you measure CTR/conversion/engagement, you declare a winner. This is the entire foundation of modern product management. Everything traces back to: pick a metric, run a test, ship the winner.

AI products break this. There is no single right answer when you're asking a model to write code, summarize a document, or answer a question. "Did the AI do a good job?" is not a question you can answer with a click-through rate.

This trips up almost every PM who comes from a traditional metrics background. They try to build dashboards that measure output quality and end up measuring the wrong thing — how often users thumbs-up/thumbs-down, how long the response was, whether the user regenerated. All of this is a proxy, and it's a bad proxy.

The actual skill here is evaluation design: figuring out, in advance, what "correct" looks like for your specific use case, and building systematic ways to check it. This is closer to QA engineering than traditional PM work. Most PMs have never had to think about it.

---

## The context window IS the product

Here's the thing nobody tells you when you start building AI products: the system prompt isn't just configuration. It's the product.

When you decide what goes in the context window — what instructions to include, what data to retrieve, how to format the retrieved content, how much of the conversation history to keep — you are making product decisions. These decisions directly affect every output the model produces. They are more consequential than most UI decisions.

Traditional PMs think about UI flows. AI PMs have to think about context architecture. What does the model need to know? In what order? With what framing? What do you leave out because it costs tokens and degrades output quality?

The teams building great AI products obsess over this. They have opinions on whether to put instructions at the top or the bottom of the context (it matters). They test different ways to structure retrieved documents. They tune how much conversation history to include based on what kinds of errors happen when they include too little versus too much.

This is not a software engineering skill. It's a product skill. But it's a product skill that requires actually understanding how models process context — which most PMs don't bother to learn because it sounds technical.

---

## Token costs are unit economics now

If you're building an AI product that runs autonomously — a coding agent, a research tool, a customer service bot — your token consumption is your cost of goods sold. It's directly analogous to server costs, database queries, third-party API calls. Every product decision you make affects it.

This became unavoidable when Anthropic moved to per-token enterprise billing earlier this year. For a while, the industry pretended that AI would be cheap and unlimited. It isn't. The pricing structure now forces every PM to ask: how many tokens does this workflow actually consume? Can we optimize the system prompt? Should we cache this context? Is this retrieval step worth the cost?

The PMs who don't think about this build products that cost $4 per user session and wonder why the unit economics don't work. The PMs who do think about it build products that cost $0.08 per session because they designed the context flow deliberately.

This sounds like an engineering problem. It isn't. Engineers can implement whatever context strategy you give them, but they're not going to make the product decisions about what to include and what to cut. That's on you.

---

## Prompts are dying. Systems are what matter.

A year ago, there was a huge market for "prompt engineering." Libraries of prompts, courses on how to write prompts, consultants charging $500/hour to improve your system prompt.

That's mostly over. Not because prompt quality doesn't matter — it still does — but because the models got so much better at following instructions that the marginal return on prompt optimization collapsed. Claude 4 will do what you ask it to do. The hard problem is no longer "how do I get the model to understand what I want." The hard problem is "how do I build a system that reliably produces good outputs at scale."

This is the shift from prompts to systems. The current generation of AI PMs needs to think like systems designers: how do inputs flow through your pipeline? where does the model make decisions? where are the failure points? what happens when the model hallucinates mid-workflow? how do you recover?

The best AI products right now — Cursor, Claude Code, Perplexity's deep research — aren't impressive because someone wrote a great prompt. They're impressive because someone designed a system with good retrieval, sensible context management, multi-step reasoning, and graceful failure handling. That design is a product decision.

---

## What Claude 4 actually changed

The current generation of models — Claude Sonnet 4.6, GPT-5.4, Gemini 3.1 — are good enough that capability is no longer the constraint on most AI products. The models can code. They can reason. They can follow complex multi-step instructions. They can handle long documents.

The constraint is now product design.

Which means the AI PM who doesn't know how to design AI systems — who treats the model as a black box that takes a prompt and produces an output — is going to be consistently out-competed by PMs who understand what's happening under the hood.

Claude 4 specifically changed two things that matter for product builders. One: it's reliable enough to run unsupervised in long agentic workflows without going off the rails. Earlier models would hallucinate tool calls or lose track of the task after 20+ steps. Sonnet 4.6 just doesn't do this the way previous versions did. Two: the context window is large enough and the model's ability to actually use what's in the context is good enough that you can put significantly more relevant information in front of it and it uses all of it, not just the last few hundred tokens.

Both of these open up product surface area that didn't exist before. They also raise the bar for what a "good" AI product looks like.

---

## My take

The AI PM job description that companies are currently posting is wrong. They're hiring for:
- Experience with LLMs (can use ChatGPT)
- Data-driven mindset (A/B tests)
- Technical background (wrote Python once)

What they actually need is someone who:
- Understands evaluation design and can build systematic quality checks
- Thinks in context architectures, not just user flows
- Has product intuition for where AI adds value versus where it adds hallucination risk
- Can hold a real conversation with ML engineers about why a workflow is behaving a certain way

The gap between those two lists is where most AI PM hires go wrong.

The good news is that the bar is low. Because most PMs are still learning ChatGPT prompts and calling themselves AI PMs, anyone who actually understands the layer below — context management, evaluation, system design, token economics — stands out immediately.

The field is early. The right skills are not that hard to develop. The PMs who put in the work to learn them now are going to be in a different conversation than the ones who didn't.

---

*Sources: [Anthropic pricing shift (April 2026)](https://fortune.com), [Cursor's product architecture](https://cursor.sh), [Claude 4 capability notes](https://anthropic.com), [AI PM hiring trends 2026 — a16z](https://a16z.com)*
