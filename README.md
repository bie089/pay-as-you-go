# pay as you go proxies: how per-GB and per-IP billing actually works, what expires, and how to buy without a subscription

Most people searching for pay-as-you-go proxies aren't looking for a lecture on network architecture. They're looking for one thing: a way to buy proxy traffic without signing up for something that charges them again next month whether they use it or not.

That's a reasonable ask, and it's also where most "no subscription" claims fall apart. A provider can sell you credits with no recurring bill and still make the deal worse than a subscription — by expiring your unused balance in 30 days, by charging an activation fee on every IP you touch, or by setting a minimum top-up that's three times larger than your actual project.

So this isn't a listicle of providers. It's a walkthrough of how consumption-based proxy billing actually works, what the fine print usually hides, and where 9Proxy's balance-based model sits in that picture — including its current packages and rates.

## Why "pay as you go" means so many different things

There's no standard definition. Three different sellers can each say "pay as you go" and mean three incompatible things:

1. **Credit balance.** You top up an account, traffic gets deducted as you use it, and the balance sits there until it runs out or expires.
2. **One-off packages.** You buy a fixed block of data or a fixed number of IPs. No renewal. When it's gone, you buy another one.
3. **Monthly plan with cancellation.** Technically no contract, but the billing rhythm is still monthly, and the price advantage usually depends on a yearly commitment.

Only the first two behave the way most buyers expect. And within those two, the deciding factor is almost never the headline price per gigabyte — it's what happens to the unused portion.

Three questions cut through most of the marketing:

- **Does unused balance expire?** If yes, how many days?
- **Is there a monthly minimum or an auto-renew toggle you have to find and switch off?**
- **Do you pay for IPs you haven't activated yet?**

A provider that answers "never," "none," and "no" is genuinely pay-as-you-go. One that answers "30 days," "yes," and "yes" is a subscription with extra steps.

## The three billing shapes you'll run into

### Per-GB (bandwidth) pricing

You buy a data block. Every request routed through the network consumes some of it. IPs themselves are free and effectively unlimited — rotation happens behind the scenes, and you generate as many endpoints as your tooling needs.

This is the model that fits work where each request is small but the volume is large: SERP checks, price monitoring, geo-verification, API polling, ad verification, and most lightweight scraping. The cost is predictable in the sense that you know your per-GB rate, but unpredictable in that you don't always know how many gigabytes a site will cost you until you run it.

The trap here is expiration. A 180-day window is workable for project-based work. A 30-day window on a 10 GB block is not.

### Per-IP pricing

You buy a quantity of residential IPs. Each activation deducts one IP from your balance, and while that IP is live you can push as much traffic through it as you like — no bandwidth metering.

This suits a completely different job: sessions that need to stay alive and consistent. Account management, cart sessions, anything behind an anti-bot layer that gets suspicious when the exit IP changes mid-session. If your bandwidth is heavy but your IP count is small, per-IP pricing can end up cheaper than any per-GB rate on the market. If your workload is thousands of short, rotated requests, it's the wrong tool.

The fine print to read here: how long does an activated IP live, and are unused IPs preserved indefinitely?

### Bundles

Some providers sell IPs and bandwidth together on one balance, usually at a discount to buying both separately. Useful when part of your workload is session-based and part is rotation-heavy, but only worth it if you'd actually have bought both meters anyway.

## Per-GB or per-IP: match the meter to the task

A quick way to decide before you spend anything:

| Your workload | Better meter | Why |
| --- | --- | --- |
| Scraping search results, prices, listings | Per GB | High request count, small payloads, rotation matters more than session stability |
| Ad verification and geo-checks | Per GB | You need many different locations, not a long-lived session |
| Managing social or marketplace accounts | Per IP | Sessions need to hold the same exit IP for hours |
| Sniping, ticketing, sneaker flows | Per IP | Short bursts, identical IP required throughout |
| Mixed agency work | Bundle | Some clients need sessions, others need raw throughput |

If you're unsure, start with a small per-GB block. A few gigabytes costs less than a takeaway meal and tells you more about a provider's success rate on your actual targets than any review will.

## Where 9Proxy fits

9Proxy is a residential proxy provider with an advertised pool of 20M+ IPs across 90+ countries, HTTP/HTTPS/SOCKS5 support, and a claimed 99.95% uptime. None of that is unusual on its own. What matters for this topic is that the business model is balance-based rather than subscription-based — there is no monthly plan to cancel, because there is no monthly plan.

It runs two product lines that map directly onto the two meters above:

**Residential Proxy by IPs** — you buy a fixed quantity of IPs. An IP is deducted only when you forward it to a local port inside the 9Proxy app. Unused IPs never expire and stay in your balance indefinitely. Once activated, an IP stays online for several hours up to about 24 hours, varying naturally because these are real residential connections. If one drops, Auto Refresh Proxy swaps in a fresh one, and Auto Rotation Proxy can rotate on a schedule you set. Bandwidth while an IP is active is unlimited.

**Residential Proxy by GB** — you buy data. You can generate unlimited endpoints, choose sticky or rotating sessions per request, authenticate with username/password or IP whitelisting, and target down to country, state, city, ZIP or ISP. Everything runs in the dashboard; the desktop app isn't required for this line. All GB plans carry 180-day validity, and on Enterprise that validity becomes unlimited.

Two details worth noting because they're the difference between real pay-as-you-go and the marketing version: the GB line has no per-IP activation cost and no IP counting, and the IP line doesn't expire what you haven't used.

👉 [Start a 9Proxy account and check the live package list in your dashboard](https://bit.ly/9-Proxy)

## 9Proxy IP-based packages

9Proxy raised IP-based and bundle prices on 1 June 2026 — its first price change in roughly three years, announced in May 2026 — while leaving GB-based pricing untouched. The figures below reflect the post-adjustment published rates.

| Package | What you get | Price | Billing type |
| --- | --- | --- | --- |
| 100 IPs | 100 residential IPs, unlimited bandwidth per active IP | $24 | One-off, no subscription |
| 500 IPs | 500 residential IPs, unlimited bandwidth per active IP | $72 | One-off, no subscription |
| 1,000 IPs (+500 bonus) | 1,000 IPs plus 500 bonus IPs | $126 | One-off, no subscription |
| 100,000 IPs | Bulk residential IPs for industrial volume | $2,300 | One-off, no subscription |
| 500,000 IPs | Largest advertised IP package | $8,625 | One-off, no subscription |

The dashboard also lists intermediate tiers — 2,500, 5,000, 15,000, 25,000 and 50,000 IPs — where the effective per-IP cost keeps dropping as the quantity rises. Those mid-tiers are exactly where the June 2026 adjustment landed, so treat any per-IP figure you find in an older review as out of date and confirm the number in your own account before buying.

👉 [Compare the current IP-based tiers](https://bit.ly/9-Proxy)

The practical takeaway from this table: the curve is steep at the bottom. Moving from 100 to 500 IPs cuts the effective per-IP price by roughly half, and the 1,000+500 package brings it down again. If you know you'll burn through a few hundred IPs over a project, buying 100 at a time is the most expensive way to do it.

## 9Proxy GB-based packages

These were not touched by the June 2026 adjustment, which makes them the more stable half of the catalogue.

| Package | Effective rate | Total price | Validity |
| --- | --- | --- | --- |
| 5 GB | $3.00 / GB | $15 | 180 days |
| 50 GB + 5 GB bonus | $2.10 / GB | $105 | 180 days |
| 100 GB | $1.50 / GB | $150 | 180 days |
| 200 GB | $1.00 / GB | $200 | 180 days |
| 1,000 GB | $0.80 / GB | $800 | 180 days |
| 2,000 GB | $0.75 / GB | $1,500 | 180 days |
| Top-volume tier | $0.68 / GB | Quoted at the 10,000 GB tier | 180 days (unlimited on Enterprise) |

The headline "from $0.68/GB" you'll see on 9Proxy's own materials refers to that top tier, not to the entry package. The smallest block is $3.00/GB, which is normal for consumption pricing — you're paying for the ability to buy small. If you only need a couple of gigabytes for a test run, the 5 GB block at $15 is the cheapest way in.

👉 [Buy a GB package and start generating endpoints](https://bit.ly/9-Proxy)

One thing to plan around: the 180-day clock applies to the whole block, not per gigabyte. If your project pauses for two months, the clock keeps running.

## Bundles: both meters on one balance

| Bundle | Contents | Price | Traffic validity |
| --- | --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 | 180 days |
| Popular | 1,500 IPs + 50 GB | $180 | 180 days |
| Pro | 5,000 IPs + 500 GB | $720 | 180 days |

Compare the Starter against buying separately: 100 IPs alone costs $24 and 5 GB alone costs $15, so $39 versus $30 — the bundle saves you about $9 if you genuinely need both. Do that arithmetic yourself for the tier you're considering, and only take the bundle if you'd otherwise buy both halves.

## Enterprise, teams, and reseller arrangements

9Proxy's Enterprise tier changes two things that matter for pay-as-you-go buyers: data validity becomes unlimited rather than 180 days, and the plan supports team mode with one owner and up to five members. Owners can share or revoke data instantly, invite or remove members, lock usage, and view activity logs; members can draw on shared bandwidth inside the team. There's also per-member traffic control and unlimited share code creation.

Enterprise and reseller pricing isn't published — you'll need to talk to sales for wholesale rates. That's the one part of this catalogue where you can't self-serve your way to a number.

## Promotions, and how the invite flow works

9Proxy runs campaign bundles rather than permanent discounts. The clearest documented example is STACK 99, which ran from 1 July to 31 August 2026: 99 GB of residential data for $99, which works out to $1.00/GB, plus a 9% coupon for your next regular GB purchase.

That coupon had real conditions attached, and they're typical of how this provider structures promos:

- The code (STACK99) locks to the account that bought the bundle and can't be transferred.
- It applies only to standard, non-promotional GB packages.
- It's single-use, non-stackable with other promo codes, and expires 30 days after the purchase that unlocked it.
- One discount per account, no matter how many bundles you buy.

The window has closed, so check the dashboard for whatever the current equivalent is instead of assuming that offer is live. You can also redeem a promo code by unticking it at checkout if you'd rather save it for a bigger restock.

On the signup side, 9Proxy uses an invite-code model, and it's their standard referral mechanism rather than anything unusual. Their affiliate programme, as described in their own outreach, advertises a 5% discount for referred users alongside commissions of up to 15% for the referrer. Confirm what applies at checkout — a referral link isn't a guarantee of a discount on every product line.

New users can also request a limited trial, subject to availability. When you ask, specify whether you want an IP-based or a GB-based trial, because they're separate products.

## What to check before you top up

A short pre-purchase checklist, applicable to 9Proxy and to anyone else:

- **Minimum spend.** Here it's $15 for the smallest GB block, $24 for the smallest IP block.
- **Expiration.** Never on unused IPs; 180 days on GB traffic; unlimited on Enterprise.
- **IP lifespan.** Several hours to about 24 hours per activated IP, which is normal for genuine residential endpoints.
- **Rotation controls.** Auto Refresh for dead IPs, Auto Rotation on custom intervals.
- **Targeting depth.** Country, state, city, ZIP and ISP on the GB line — check this against the specific sites you're targeting, since city-level availability is never guaranteed at 100% on residential networks.
- **Payment methods.** Credit cards, bank cards, crypto (USDT, BTC, ETH, LTC, DOGE and others), Alipay, Apple Pay, Google Pay.
- **Support hours.** 24/7 chat and email; dedicated account managers sit at the upper tiers.

## What third-party reviews actually say

Independent comparisons rank 9Proxy in the budget residential tier. One 2026 cost survey puts its typical residential rate at roughly $1.30–$2.00/GB at standard volumes — noticeably above the $0.68/GB headline, because that headline only applies at the top tier. The same survey ranks cost as DataImpulse (around $1/GB) below 9Proxy, with ProxyScrape above it at $2–4/GB.

The same source rates success rates at 99%+ on unprotected Tier 1 targets, 90–95% on moderately protected sites, and 70–85% on heavily protected ones — the last figure being the honest limit of any budget provider without a dedicated unlocking layer. It also notes 9Proxy residential IPs pass GA4 filtering, and that support is community-level at the lower tiers.

Geekflare's 2026 review of the network frames the dual billing model as the main structural advantage: you're not forced into a pricing shape that doesn't match your workload, and the IP-based unlimited bandwidth option works well for longer engagements.

The caveats worth carrying forward: no anti-detection toolkit, limited city-level targeting, and no enterprise-grade SLA at small volumes. If your targets are Tier 3 sites with aggressive bot defences, budget residential is the wrong category regardless of provider.

## Quick answers

**Can I use proxies without a monthly subscription?** Yes — with a balance-based provider there's no recurring charge at all. You top up, spend down, and top up again when you need to.

**Do unused proxies expire?** At 9Proxy, unused IPs don't expire and stay in your balance indefinitely. GB traffic carries a 180-day window, extended to unlimited on Enterprise.

**What happens if an activated IP drops?** Auto Refresh Proxy replaces it with a fresh one automatically, or Auto Rotation rotates on a schedule you configure.

**Is the cheapest per-GB rate the one I'll pay?** Only at the top volume tier. Entry pricing is $3.00/GB on the 5 GB block.

**Do I need to install an app?** The GB line runs entirely in the dashboard. The IP line uses local port forwarding through the 9Proxy app.

**Is there a free trial?** Limited trials are offered to new users depending on availability — ask support, and say whether you want IP-based or GB-based.

## Bottom line

Pay-as-you-go proxy billing rewards one habit: reading what happens to the balance you didn't use. Everything else — the per-GB rate, the pool size, the country count — is secondary to whether the unused portion survives and whether the IPs you've paid for get charged before you activate them.

9Proxy handles both of those correctly: no subscription, unused IPs preserved indefinitely, 180-day validity on bandwidth. Its weakest spot is entry pricing, where $3.00/GB looks expensive next to its own $0.68/GB headline, and success rates on heavily protected targets sit in the 70–85% range typical of the budget tier.

If your workload is Tier 1–2 targets, a small GB block is the cheapest way to find out whether this provider works for you. If your work is session-based rather than request-based, the 500-IP package at $72 is where the per-IP curve starts making sense.

👉 [Sign up with 9Proxy and pick the package that matches your workload](https://bit.ly/9-Proxy)
