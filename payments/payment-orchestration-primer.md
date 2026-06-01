# How Payment Orchestration Actually Works (And Why Stripe Isn't Enough)

Nearly 1 in 13 online payments fails. Not because the customer doesn't have the money. Not because the card is expired. Because the infrastructure routing that payment to the bank is dumb, brittle, and built for one provider's world.

That's the problem payment orchestration exists to solve. And it's a bigger deal than most people outside fintech realize.

---

## The Stripe ceiling

Stripe is genuinely excellent. For a startup processing $500K a year, it's close to perfect. Clean API, fast onboarding, great developer experience. The docs are better than most companies' actual products.

Then you scale.

You expand to Latin America and realize Stripe doesn't support PIX. You move into Southeast Asia and half your transactions are routing through suboptimal acquirers. Your decline rate creeps up. Finance wants to know why. Your payments engineer spends three weeks debugging an integration with a local provider. You realize Stripe's radar is flagging good customers in certain markets. You want to A/B test checkout flows but Stripe's system doesn't let you.

Every problem is solvable. Each solution requires a separate integration. Then another. Then a team to maintain them.

This is exactly what happened to Airbnb. They operate in 220+ countries. Rolling out 20 local payment methods took a 14-month engineering sprint, a centralized observability framework, and a connector-based PSP architecture. They essentially built a mini-orchestration layer from scratch because the alternative was chaos.

Uber did the same thing from a different angle. Every product line — rides, Eats, rentals — was handling payments differently. Their solution was a single orchestration layer called Unified Checkout. One system. All products route through it. Millions of transactions a day, consistent logic.

At scale, reinventing this wheel costs tens of millions in engineering time. Which is why the orchestration market exists.

---

## What orchestration actually does, technically

Payment orchestration sits between your product and all your payment providers. Think of it as a smart switching layer. Your checkout sends a payment request to the orchestrator. The orchestrator decides where to send it, how to authenticate it, how to retry it if it fails, and how to reconcile it afterward.

The key components:

**Smart routing.** Not all PSPs are equal in all contexts. An orchestrator tracks historical authorization rates per PSP, broken down by card type, issuer country, BIN range, transaction size, and dozens of other signals. When a transaction comes in, it routes to the acquirer most likely to approve it. This alone can lift authorization rates by several percentage points — which at scale translates directly to revenue recovered.

**Waterfall routing.** When a transaction fails at the first PSP, waterfall logic automatically retries it with a second provider. Then a third if needed. Cascading routing recovers 10-15% of soft-declined transactions that would otherwise be lost. Soft declines aren't fraud rejections — they're often temporary issuer issues, network timeouts, or capacity problems. A second attempt through a different acquirer often goes through clean.

**Decline recovery.** More sophisticated than a simple retry. Orchestrators analyze decline codes to decide the right recovery path. A "do not honor" code from a US issuer means something different than an insufficient funds code from a European bank. Smart orchestrators know the difference and don't just blindly cascade — they pick the right follow-up based on the failure mode.

**3DS and SCA.** 3D Secure is the authentication layer that pops up the "Verified by Visa" or bank app confirmation on high-risk transactions. Getting 3DS right is genuinely hard. Challenge too many transactions and you kill conversion. Challenge too few and you take on fraud liability. Orchestrators apply 3DS selectively using risk signals, exemption logic, and transaction context — threading the needle between SCA compliance and checkout friction.

**Tokenization and vaulting.** When a customer saves their card, the raw PAN (primary account number) gets replaced with a token. The orchestrator's vault holds the mapping. This matters for two reasons. First, security — PCI scope shrinks dramatically when no part of your stack ever touches raw card data. Second, PSP portability. If your tokens live inside Stripe's vault, switching PSPs means losing all your stored payment methods. Merchant-owned vaults break that dependency.

**Network tokenization** goes a layer deeper. Instead of just abstracting the PAN on your side, the card networks (Visa, Mastercard) issue their own tokens tied to specific merchants and devices. These tokens get automatic card updates when a card expires. Authorization rates improve by 4-6% on average. Fraud rates drop by around 28%. The issuer trusts a network token more than a raw PAN, and that trust shows up in approvals.

---

## The data problem nobody talks about

Here's the thing that doesn't get discussed enough: payments generate a lot of signal that most companies never use.

Primer captures 400+ data points per transaction. Not just success/fail. Card type, issuer, device, IP, time of day, browser fingerprint, transaction history, retry pattern. That's the raw material for everything from fraud scoring to routing optimization to identifying checkout drop-off points.

When you're integrated with a single PSP, you only see their slice of that data. You can't benchmark your decline rates against industry norms. You can't tell if your rates are bad because of your routing or because of your customer profile. You're flying half blind.

An orchestration layer that aggregates data across PSPs gives you the full picture. Which is why Primer Companion — their AI agent launched in late 2025 — is an interesting move. The pitch is: the platform already has the data and the integrations, so why not let an AI agent operate within it autonomously? Set parameters, let it optimize routing, surface anomalies, recommend A/B tests on checkout flows.

The $100M Series C (led by Sofina, with Balderton, Accel, ICONIQ, and Tencent backing) is largely a bet on that AI layer getting built out and capturing the US market. They want US revenue to hit a third of total revenue by 2028. Right now it's primarily a European story.

---

## The numbers that justify the category

Businesses relying on a single PSP experience payment disruptions at a 42.4% rate. That's not a small edge case — that's nearly half of single-PSP merchants hitting meaningful failures.

Switch to 2-4 PSPs with smart routing and that number drops sharply. Decline rates under 3% are achievable. The companies hitting above 8% decline rates are almost always single-PSP, basic-routing setups.

Subscription businesses and e-commerce are the most exposed — decline rates can hit 30% in some categories. A few percentage points of improvement at scale isn't nice-to-have. It's millions of dollars recovered per year.

---

## My take

There's a version of this story where payment orchestration is just plumbing — infrastructure that matters but isn't interesting. I don't think that's right.

The more interesting version is that orchestration is actually a data play dressed up as infrastructure. The company that sits between merchants and PSPs globally, processing billions of transactions, accumulates signal that nobody else has. Decline patterns by issuer. Fraud signals by device profile. Conversion rates by checkout variant. Regional nuance in how authentication flows perform.

That data advantage is what makes the AI bet from Primer credible. They're not trying to build an LLM. They're building an agent that operates on payment-specific data that they uniquely possess. Primer Companion isn't useful because it can write code — it's useful because it knows your authorization rate by BIN range and can tell you which acquirer to switch for your German Mastercard traffic.

Stripe has been quietly adding orchestration-adjacent features — multi-acquirer routing, smarter retry logic. But it's cards-only, and it's still within Stripe's ecosystem. The moment you need PIX, GrabPay, SEPA Direct Debit, and UPI in the same checkout, you've outgrown the native tools.

The real competition isn't Stripe vs. Primer. It's Primer vs. merchants deciding to build their own orchestration layer in-house. That decision gets made at a certain scale threshold. Below it, you don't need orchestration. Above it, you usually wish you'd adopted it sooner. The interesting question is whether AI-native orchestration moves that threshold down — making the economics work for mid-market merchants who previously couldn't justify the overhead.

My guess is yes. And whoever figures out the agent interface first — autonomous routing decisions within merchant-set guardrails — owns a genuinely sticky layer of the global commerce stack.

That's not a bad place to be.
