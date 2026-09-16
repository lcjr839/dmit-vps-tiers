# web hosting service: DMIT VPS plans, pricing tiers, and when premium CN2 GIA routing actually pays off

When you type "web hosting service" into a search box, what you're really after is usually more specific than the phrase suggests. You might be looking for somewhere to put a small business site, a development sandbox, a game server, or — increasingly common — a server that can actually reach users in mainland China without the latency and packet loss that most generic providers deliver. This article focuses on that last scenario, because it's where the choice of provider matters most, and where **DMIT** has built its reputation.

DMIT is a VPS and cloud instance provider that operates its own infrastructure in Los Angeles, Hong Kong, and Tokyo, with a clear specialty: cross-border connectivity into the Asia-Pacific region, and mainland China in particular. If your hosting problem is "my users in China keep complaining the site is slow or unreachable," DMIT is one of the names that comes up again and again in technical communities — for good reason. Below I'll walk through what they actually sell, how the plans are structured, what you'll pay, and how to tell whether any of it is worth it for your situation.

## Why DMIT shows up when people talk about China-facing hosting

Most big-name cloud providers (DigitalOcean, Vultr, Linode/Akamai) run excellent networks for North America and Western Europe. Their routes into China, however, go through congested international gateways where latency routinely hits 200–300ms and packet loss spikes during peak hours. Domestic Chinese clouds (Alibaba, Tencent) solve that, but they're complicated for international users and often require a Chinese business license.

DMIT sits in the gap. They peer directly with all three major Chinese carriers — China Telecom (AS4809), China Unicom (AS9929), and China Mobile International (AS58807) — and on their top-tier network they additionally use China Telecom's CN2 GIA premium backbone. That combination is what differentiates them from commodity hosting, and it's why people who've been burned by cheap providers end up looking at DMIT.

## The three network tiers: Premium, Eyeball, Tier 1

This is the single most important thing to understand about DMIT's pricing. Every plan exists in three network variants, and the tier — not the hardware — is what drives most of the price difference.

**Premium (Pro)** is the top tier. It combines Tier 1 transit with premium transit partners, DMIT's own backbone, and CN2 GIA. DMIT positions it as the best routing quality to mainland China and the broader Asia-Pacific, with lower latency, fewer hops, and significantly reduced packet loss. It's the most expensive option, and it's the one you want if the end-user experience in China or APAC directly affects your project.

**Eyeball (EB)** is the middle ground. It pairs Tier 1 transit with "reasonable effort" China routing via CMIN2/CMI and other Chinese eyeball ISPs. It doesn't carry the same premium guarantees as the Pro tier, but DMIT says it provides noticeably better access for Chinese residential users than plain Tier 1. A practical budget option for services with a global but China-aware audience.

**Tier 1 (T1)** is standard international routing with no China optimization. It's the cheapest series, focused on clean intra-APAC and trans-Pacific routing. DMIT recommends it for backups, CI/CD, VPN relays, and cost-sensitive compute where China reachability isn't a priority.

One caveat worth noting: DMIT's terms state that IPs assigned to Tier 1 products are not guaranteed to be available in all countries or regions, and they explicitly call out China, Russia, and countries with national network censorship. If you buy T1 expecting it to work in China, that's on you.

## Three locations, three hardware platforms

DMIT operates in **Los Angeles, Hong Kong, and Tokyo**. Each location offers all three network tiers, so you're really choosing along two axes: where your server sits physically, and how its traffic gets routed.

On top of that, DMIT runs three hardware platforms that further affect price and performance:

- **AS3 (AMD EPYC 7003, Zen 3)** — their "best value" platform. Mature, field-proven, the most competitive price-per-core. Good for staging, entry-level, and budget-conscious workloads.
- **AN4 (AMD EPYC 9004, Zen 4)** — the balanced workhorse. Strong per-core performance with high core density.
- **AN5 (AMD EPYC 9005, Zen 5)** — the flagship. Latest IPC, DDR5, PCIe 5.0 NVMe. Best for high-traffic sites, databases, and latency-sensitive apps.

The same plan name (e.g. MINI) can be priced differently depending on which hardware platform it runs on, with AN5 commanding a premium over AS3. The pricing tables below reflect what DMIT currently lists; note that DMIT's own pricing page carries the disclaimer that products and prices may be adjusted and are for reference only.

## Full plan comparison: Los Angeles

Los Angeles is DMIT's flagship location and offers the widest selection. The LAX AS3 series is still being built out, and DMIT notes you may see reduced disk performance and a lower SLA than on their mature platforms during this period.

**Premium Network (LAX.Pro) — AS3 platform**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| TINY | 1 vCore | 2GB | 20GB | 1000GB | 1Gbps | $10.90/mo | [View LAX Pro TINY](https://bit.ly/DmiT) |
| Pocket | 2 vCore | 2GB | 40GB | 1500GB | 4Gbps | $16.90/mo | [View LAX Pro Pocket](https://bit.ly/DmiT) |
| STARTER | 2 vCore | 2GB | 80GB | 3000GB | 10Gbps | $34.90/mo | [View LAX Pro STARTER](https://bit.ly/DmiT) |
| MINI | 4 vCore | 4GB | 80GB | 5000GB | 10Gbps | $62.90/mo | [View LAX Pro MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 160GB | 7000GB | 10Gbps | $87.90/mo | [View LAX Pro MICRO](https://bit.ly/DmiT) |
| MEDIUM | 6 vCore | 8GB | 160GB | 15000GB | 10Gbps | $199.90/mo | [View LAX Pro MEDIUM](https://bit.ly/DmiT) |

**Premium Network (LAX.AN5.Pro) — flagship Zen 5 platform**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.AN5.Pro.MINI | 4 vCore | 4GB DDR4 | 80GB | 5000GB | 10Gbps | $79.90/mo | [View LAX AN5 Pro MINI](https://bit.ly/DmiT) |
| LAX.AN5.Pro.MICRO | 4 vCore | 4GB DDR4 | 160GB | 7000GB | 10Gbps | $110.90/mo | [View LAX AN5 Pro MICRO](https://bit.ly/DmiT) |
| LAX.AN5.Pro.MEDIUM | 6 vCore | 8GB DDR4 | 160GB | 15000GB | 10Gbps | $289.90/mo | [View LAX AN5 Pro MEDIUM](https://bit.ly/DmiT) |

**Eyeball Network (LAX.EB)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTER | 2 vCore | 2GB | 80GB | 5000GB | 10Gbps | $29.90/mo | [View LAX EB STARTER](https://bit.ly/DmiT) |
| MINI | 4 vCore | 4GB | 80GB | 10000GB | 10Gbps | $58.88/mo | [View LAX EB MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 160GB | 14000GB | 10Gbps | $74.99/mo | [View LAX EB MICRO](https://bit.ly/DmiT) |

**Tier 1 Network (LAX.T1)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTER | 1 vCore | 2GB | 40GB | 4000GB | Based on performance | $12.90/mo | [View LAX T1 STARTER](https://bit.ly/DmiT) |
| MINI | 2 vCore | 2GB | 60GB | 8000GB | Based on performance | $21.90/mo | [View LAX T1 MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 80GB | 16000GB | Based on performance | $32.90/mo | [View LAX T1 MICRO](https://bit.ly/DmiT) |

A useful pattern: at similar hardware specs, Eyeball gives you roughly 1.5–2x the monthly traffic of Premium at a slightly lower price, and Tier 1 gives you 4–5x the traffic at a much lower price. You're trading China routing quality for raw transfer budget.

## Full plan comparison: Hong Kong

Hong Kong is the lowest-latency option for China-facing workloads, and the prices reflect that. Pro plans here are notably more expensive than LA because bandwidth in HK is costly and the China-direct advantage is largest.

**Premium Network (HKG.Pro)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTER | 1 vCore | 2GB | 40GB | 800GB | 1Gbps | $79.90/mo | [View HKG Pro STARTER](https://bit.ly/DmiT) |
| MINI | 2 vCore | 2GB | 60GB | 1200GB | 1Gbps | $119.90/mo | [View HKG Pro MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 80GB | 1600GB | 1Gbps | $159.90/mo | [View HKG Pro MICRO](https://bit.ly/DmiT) |

**Eyeball Network (HKG.EB v2)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTERv2 | 1 vCore | 2GB | 40GB | 2000GB | 2Gbps (no guarantee) | $59.90/mo | [View HKG EB STARTERv2](https://bit.ly/DmiT) |
| MINIv2 | 2 vCore | 2GB | 60GB | 3000GB | 2Gbps (no guarantee) | $89.90/mo | [View HKG EB MINIv2](https://bit.ly/DmiT) |
| MICROv2 | 4 vCore | 4GB | 80GB | 4000GB | 4Gbps (no guarantee) | $129.90/mo | [View HKG EB MICROv2](https://bit.ly/DmiT) |

**Tier 1 Network (HKG.T1)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTER | 1 vCore | 2GB | 40GB | 4000GB | Based on performance | $12.90/mo | [View HKG T1 STARTER](https://bit.ly/DmiT) |
| MINI | 2 vCore | 2GB | 60GB | 8000GB | Based on performance | $21.90/mo | [View HKG T1 MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 80GB | 16000GB | Based on performance | $32.90/mo | [View HKG T1 MICRO](https://bit.ly/DmiT) |

Note how HKG Tier 1 plans cost the same as LAX Tier 1 — the China optimization premium only applies to Pro and EB tiers. If you want a cheap Hong Kong server for non-China work, T1 is genuinely competitive.

## Full plan comparison: Tokyo

Tokyo is a middle ground: closer to China than LA, cheaper than Hong Kong on the Pro tier, with strong intra-Asia connectivity.

**Premium Network (TYO.Pro)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTER | 1 vCore | 2GB | 40GB | 500GB | 1Gbps | $39.90/mo | [View TYO Pro STARTER](https://bit.ly/DmiT) |
| MINI | 2 vCore | 2GB | 60GB | 1000GB | 1Gbps | $79.90/mo | [View TYO Pro MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 80GB | 2000GB | 1Gbps | $159.90/mo | [View TYO Pro MICRO](https://bit.ly/DmiT) |

**Eyeball Network (TYO.EB)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTER | 1 vCore | 2GB | 40GB | 2000GB | 2Gbps (no guarantee) | $55.90/mo | [View TYO EB STARTER](https://bit.ly/DmiT) |
| MINI | 2 vCore | 2GB | 60GB | 3000GB | 2Gbps (no guarantee) | $85.90/mo | [View TYO EB MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 80GB | 4000GB | 4Gbps (no guarantee) | $119.90/mo | [View TYO EB MICRO](https://bit.ly/DmiT) |

**Tier 1 Network (TYO.T1)**

| Plan | CPU | RAM | SSD | Bandwidth | Port | Price (Monthly) | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| STARTER | 1 vCore | 2GB | 40GB | 4000GB | Based on performance | $12.90/mo | [View TYO T1 STARTER](https://bit.ly/DmiT) |
| MINI | 2 vCore | 2GB | 60GB | 8000GB | Based on performance | $21.90/mo | [View TYO T1 MINI](https://bit.ly/DmiT) |
| MICRO | 4 vCore | 4GB | 80GB | 16000GB | Based on performance | $32.90/mo | [View TYO T1 MICRO](https://bit.ly/DmiT) |

Tokyo T1 again matches LAX and HKG T1 pricing exactly, which tells you the T1 product is a standardized international-routing SKU regardless of city.

## Annual promotional plans

Beyond the monthly-billed tiers above, DMIT periodically offers annual promotional SKUs that aren't always visible in the standard pricing grid. Community sources and DMIT's own promo pages have referenced plans along these lines for LAX Premium:

- **LAX.Pro.WEE** — 1 vCore, 1GB RAM, 20GB SSD, 500GB/mo at 500Mbps, around $36.9/year
- **LAX.Pro.MALIBU** — 1 vCore, 1GB RAM, 20GB SSD, 1TB/mo at 1Gbps, around $49.9/year
- **LAX.Pro.PalmSpring** — 2 vCore, 2GB RAM, 40GB SSD, 2TB/mo at 2Gbps, around $100/year

These annual plans are the cheapest way to get CN2 GIA routing, but they sell out and restock unpredictably. If you see one in stock, that's the moment to grab it. You can check current availability directly: 👉 [Browse DMIT's current plans and stock](https://bit.ly/DmiT).

## Discounts and promo codes: what to expect

DMIT does release discount codes from time to time, and their terms state these codes only apply to new customers (with separate codes occasionally issued to existing customers as business compensation). Based on third-party tracking and DMIT's own promo pages, recurring-discount codes have historically targeted specific product lines — for example, percentage-off recurring discounts on LAX Eyeball quarterly/annual billing, Tokyo Tier 1, Hong Kong Tier 1 annual billing, and HKG/TYO Premium quarterly-or-longer billing.

I'm deliberately not listing specific code strings here, because promo code availability changes frequently and I can't verify in real time which codes are currently active on DMIT's official order pages. The reliable approach is to check the DMIT promotions page or the order page for the plan you want — valid codes appear there when active. Applying a code that doesn't belong to you (DMIT's terms explicitly call this out) can get your service suspended and your refund refused.

The one structural discount worth knowing about: longer billing cycles often unlock bigger recurring discounts, and some product lines (notably HKG Tier 1 annual) have historically come with both a deep percentage discount and upgraded specs. If you're confident you'll use the service for a year, annual billing is almost always the better deal on DMIT.

## What "unmanaged" actually means here

DMIT's services are unmanaged. Their terms set the expectation that support ticket replies can take up to 72 hours, though community reports generally describe faster responses for legitimate technical issues. What you get is full root access via SSH, your choice of Linux distribution (Ubuntu, Debian, CentOS, AlmaLinux, Rocky, Fedora, openSUSE, Arch, Alpine and others are one-click installs), and the ability to mount ISO images, take snapshots, and configure automated backups.

What you don't get is a managed control panel, one-click WordPress installation, or hand-holding on server administration. If you're comfortable in a terminal, this is fine. If you wanted cPanel and someone to fix your PHP errors, DMIT isn't the right product.

The client portal handles plan management, billing, resource monitoring, IP replacement requests, and reinstallation. Snapshots and online backups are available; online backup storage starts at $0.45/GB per month.

## SLA, refunds, and IP replacement

DMIT's current SLA is 99% availability. The compensation structure is straightforward: drop below 99% in a month and you get half a month's credit; below 95% earns a full month; below 90% earns two months. You have to notify them within three days of the incident following the SLA procedure, or you waive the credit.

Refunds are limited and conditional. Full refunds (minus payment-gateway transaction fees) are available if the service is purchased no more than 3 days ago and you've used no more than 30GB of transfer. Partial refunds are available within 30 days, calculated based on either remaining transfer or remaining service time, whichever is lower. There's a hard limit of three refunds on the same series of products per natural person, and no refunds at all if your service has been DDoSed, if you complain about "network not good enough," if your IP's geographic location isn't what you wanted, or if you've used more than 3GB and then claim your IP isn't reachable in some region.

IP replacement is a real concern for China-facing hosting because the Great Firewall blocks IPs unpredictably. DMIT's policy: on Premium and Eyeball profiles, free IP replacement every 15 days (or every 7 days with their `IP Care+` service); immediate replacement anytime for $5. On Tier 1, IP replacement costs $5 each time with 7 days between replacements, and there's an `IP Guarantee+` addon for first-connection guarantees in sensitive regions. Premium and Eyeball profiles guarantee first connection is reachable in all countries unless there's a force-majeure internet disruption.

## DMIT vs the alternatives

If you're comparing DMIT to other options for Asia-Pacific or China-facing hosting, the field looks roughly like this:

- **BandwagonHost / BuyVM** — cheaper CN2 GIA options, but stock is less consistent and the network isn't as comprehensively engineered.
- **Vultr / DigitalOcean / Linode** — solid global networks, no real China route optimization. Fine if your users aren't in China.
- **Alibaba Cloud / Tencent Cloud** — native China infrastructure with the best possible China latency, but complex for international buyers and certain products require a Chinese business license.
- **Generic budget VPS providers** — cheaper, but you'll get commodity routing that performs poorly into China during peak hours.

DMIT's actual niche is reliable cross-border China connectivity without the regulatory complexity of domestic Chinese cloud. If that's not your problem, they're overpriced. If it is, they're one of the cleaner options.

## Who should buy DMIT, and who shouldn't

DMIT makes sense if your users are in mainland China, Hong Kong, or Taiwan and latency actually matters — a game server, a business site with APAC customers, a live-streaming relay, a real-time application where 50ms versus 200ms is the difference between usable and broken. It also makes sense if you've already tried a cheaper provider and discovered the hard way that "CN2 GIA" on a $3/month VPS isn't the same as CN2 GIA on dedicated premium transit.

DMIT is probably overkill if all your users are in North America or Western Europe, if you're hosting a low-traffic personal blog, if you need Windows VPS (DMIT is Linux-focused), or if you need managed hosting with a control panel and responsive human support for non-technical issues.

The honest framing: you're paying for premium routing. If that routing solves a real problem for you, the value is obvious and the price is justified. If it doesn't, you're paying a premium for capability you won't use, and a generic provider at a third of the cost will serve you better.

## FAQ

**Is DMIT suitable for beginners?** Only if you're comfortable with SSH and Linux server administration. There's no managed control panel by default, though you can install cPanel, Plesk, or any panel yourself.

**What happens if I exceed my bandwidth limit?** DMIT's terms say they may rate-limit, suspend, or charge based on the Fair Use Policy. In practice, excess traffic is typically throttled rather than cutting your connection or charging surprise overage fees, but it depends on the plan and circumstances.

**Can I upgrade my plan later?** Yes, plan upgrades are handled through the client portal. Downgrades and plan changes may involve modification fees or require re-initiating service.

**Is there a money-back guarantee?** Only a narrow one — full refund within 3 days and under 30GB transfer used, partial refund within 30 days. Read the refund policy carefully before buying, because the exclusion list is long.

**Do DMIT plans include DDoS protection?** Basic DDoS protection is included on the plans listed above. Higher-tier mitigation capacity is available on select plans and profiles.

**Which location should I pick?** For China-facing workloads where lowest latency matters most, Hong Kong. For a balance of China reachability and cost, Tokyo. For the widest plan selection and lowest entry price on CN2 GIA, Los Angeles.

## Getting started

The cheapest way to test DMIT's network without a major commitment is one of the annual LAX Premium promotional plans when they're in stock — a year of CN2 GIA routing for roughly the cost of a couple of months on a generic budget VPS, and you're getting something fundamentally different in terms of network quality. If you're not sure which tier fits, start with Tier 1 or Eyeball at a lower price point, validate that DMIT's platform works for you, and upgrade to Premium once you've confirmed the network quality is what you need.

👉 [View all current DMIT plans, pricing, and stock availability](https://bit.ly/DmiT)

DMIT isn't the right web hosting service for every project, and it's priced accordingly. But for the specific problem it's built to solve — reliable, low-latency connectivity between North America, Asia-Pacific, and mainland China — it does the job that commodity providers consistently fail at. If that's the problem you arrived here trying to solve, the plans above are where to start.
