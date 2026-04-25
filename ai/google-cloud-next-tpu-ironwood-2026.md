# Google just split its TPU in two, and it might be the smartest thing they've done in the AI chip war

Ironwood for inference. TPU 8t for training. TPU 8i for inference. Google's not trying to build one chip to rule them all anymore - they're building specialized weapons.

---

Google Cloud Next just wrapped up in Las Vegas, and the biggest announcement isn't a model or an agent or another Gemini update. It's hardware. Specifically, Google just revealed that they're splitting their TPU lineup into two separate chips, each designed for a fundamentally different job. And the reasoning behind it tells you exactly where the AI industry is heading.

## The chips

**Ironwood (7th gen TPU)** - Google's first TPU designed from the ground up for inference. Not training. Just inference. It can scale up to 9,216 chips in a single superpod, connected via ICI networking running at 9.6 Tb/s. More than 4x better performance per chip compared to the previous generation. Nearly 2x improvement in power efficiency.

**TPU 8t** - 8th generation, designed specifically for training. This is the chip you use to build the next Gemini model.

**TPU 8i** - 8th generation, designed specifically for inference. This is the chip that serves Gemini to a billion users.

Both 8th gen chips deliver 2x better performance-per-watt over Ironwood.

## Why splitting matters

Every other chip company - Nvidia included - builds GPUs that are supposed to do everything. Training and inference on the same hardware. It works, but it's a compromise. Training workloads care about raw throughput, massive memory bandwidth, and the ability to move gradients across thousands of chips simultaneously. Inference workloads care about latency, cost per query, and power efficiency.

These are different engineering problems. Google's betting that designing separate chips for each will outperform the one-chip-does-everything approach.

This is the same logic that led Apple to split their chips into performance and efficiency cores. It's the same logic that led AWS to build Graviton for general compute and Inferentia for ML inference separately. Specialization wins.

## The Nvidia question

Nvidia's H100 and B200 are still the default choice for most AI companies. They're versatile, well-supported, and CUDA is an unbreakable moat for now. But Google doesn't need to beat Nvidia in the open market. They need to beat Nvidia inside Google Cloud. And for their own workloads - Gemini, Search, YouTube recommendations - specialized TPUs are already cheaper and faster than renting Nvidia hardware.

The real threat to Nvidia isn't that someone builds a better general-purpose chip. It's that the biggest AI consumers - Google, Amazon (Trainium), Microsoft (Maia) - all build their own specialized chips and stop buying Nvidia entirely for their core workloads. Death by a thousand custom chips.

## My take

The training vs inference split is the most underrated trend in AI infrastructure right now. Last year, everyone was obsessed with training - who has the most H100s, who can train the biggest model. This year, the conversation has shifted. Models are big enough. The bottleneck is serving them efficiently to billions of users at reasonable cost.

Google's Ironwood and TPU 8i are a direct response to this shift. When 90% of your compute spend is inference (which it is for Google), it makes zero sense to run it on hardware that was designed for training.

The companies that figure out inference economics first win the AI endgame. Google just showed they understand this. Whether the rest of the industry follows depends on how many more billion-dollar GPU orders Nvidia can close before the custom chip wave catches up.
