# pay per gb proxies: How GB-based billing works, what residential bandwidth really costs per gigabyte, and how to avoid paying for traffic you never use

Search "pay per gb proxies" and you'll get a pricing page that says the same three words as four other providers, a chart with numbers that don't line up, and no clear answer to the only question that matters: what will this actually cost me this month?

The short version: paying per gigabyte means you buy traffic instead of IP addresses. You can spin up as many endpoints as you want, rotate as hard as you want, and your bill tracks data consumed. That model is genuinely good for some workloads and quietly expensive for others. Below is what the numbers look like across the market right now, how 9Proxy structures its GB plans, and where the fine print tends to bite.

## What "pay per GB" actually means on a proxy pricing page

Residential proxy billing comes in two shapes, and providers sometimes blur them.

**Pay per IP** gives you a fixed number of residential IPs, usually with unlimited bandwidth on each one while it's active. You're buying addresses, not data. Ten IPs at 50 GB each costs the same as ten IPs at 3 GB each.

**Pay per GB** gives you a bucket of traffic. You generate endpoints freely, and each request drains the bucket by however much data it transfers. No IP inventory to manage, no activation fees, no "you used 8 of your 10 IPs" anxiety.

Most people typing "pay per gb proxies" into a search box are looking for the second one, often because their last provider billed per IP and they watched addresses sit half-idle while the project burned through data unevenly.

There's a third thing to watch for: providers that advertise "pay per GB" but charge it as a subscription. You commit to a monthly volume, and unused traffic evaporates at the end of the cycle. Prepaid balance models behave differently, and the difference shows up in month three when your project has a slow week.

## Where your gigabytes actually go

Bandwidth accounting isn't mysterious, but it isn't intuitive either.

Every response your proxy fetches counts, including headers and any overhead on the connection. A text-only API response might be 40 KB. The same page with images, fonts, and tracking scripts can be 2–5 MB. Scrape 100,000 product pages at 2 MB each and you've moved 200 GB. At a $1.50/GB rate that's $300; at $3.00/GB it's $600. Same code, same data, twice the bill.

Two habits change the math more than provider choice does:

1. **Block images, media, and fonts** unless the task needs them. Rendering a full page to read one price field is the single most common way people inflate bandwidth spend.
2. **Match rotation to the job.** A rotating session that changes IP on every request costs you more in handshakes and retries than a sticky session that holds an IP for ten minutes on a site that doesn't care.

Neither trick saves you anything if your plan expires before you use it, which is the part most pricing pages bury.

## Who GB billing fits, and who should pay per IP instead

Paying per gigabyte tends to suit:

- Scraping and data collection where request volume is high and payloads are small
- Ad verification and geo-checking, where you're loading a page from fifteen cities and moving very little data
- API polling, price monitoring, SERP checks
- Projects with uneven or unpredictable monthly volume, since a prepaid balance doesn't force you to consume on a schedule
- Teams that don't want to manage IP inventory at all

Paying per IP usually wins when:

- You run long sessions on the same IP for account work
- You're streaming or transferring heavy files, where unlimited bandwidth per IP caps your downside
- Your workload is steady and bandwidth-heavy, so a fixed cost beats a variable one

If you're doing sustained multi-hour sessions on a handful of identities, per-IP with unlimited bandwidth is almost always cheaper than paying per gigabyte for the same traffic. If your task looks like "hit 50,000 endpoints from 40 countries and move 8 GB doing it," per-IP is a money pit and per-GB is the obvious pick.

## What residential bandwidth costs across the market

Entry rates below are published pay-as-you-go residential pricing, not the discounted enterprise tier you'd get after a sales call.

| Provider | Published residential rate |
| --- | --- |
| Bright Data | $8.40/GB pay-as-you-go |
| IPRoyal | ~$7/GB, down to ~$1.75/GB in bulk |
| Decodo | $3.50/GB entry |
| Proxyon | from $4.00/GB, down to $1.50/GB at volume |
| Proxidize | from $1/GB, lower at volume |
| 9Proxy | $3.00/GB on the smallest pack, down to $0.68/GB at 10,000 GB |

The spread is roughly 12x between the cheapest and most expensive entry rates, which tells you the label "residential proxy" covers a very wide range of infrastructure. What you're really comparing is pool cleanliness, targeting depth, and whether the cheap rate applies to your first purchase or only to a five-figure commitment. Several providers make their headline number reachable only at volumes a solo operator will never hit.

## 9Proxy's GB plans, in full

9Proxy runs a balance-based system rather than a subscription. You add traffic to your account and consume it when your work needs it. Nothing here renews automatically, and there's no monthly minimum.

| GB Package | Rate per GB | Total | Validity | Purchase |
| --- | --- | --- | --- | --- |
| 5 GB | $3.00 | $15 | 180 days | [Start with 5 GB of traffic](https://bit.ly/9-Proxy) |
| 50 GB + 5 GB bonus | $2.10 | $105 | 180 days | [Get the 50+5 GB pack](https://bit.ly/9-Proxy) |
| 100 GB | $1.50 | $150 | 180 days | [Buy 100 GB](https://bit.ly/9-Proxy) |
| 200 GB | $1.00 | $200 | 180 days | [Buy 200 GB](https://bit.ly/9-Proxy) |
| 1,000 GB | $0.80 | $800 | 180 days | [Buy 1,000 GB](https://bit.ly/9-Proxy) |
| 2,000 GB | $0.75 | $1,500 | 180 days | [Buy 2,000 GB](https://bit.ly/9-Proxy) |
| 3,000 GB (Enterprise) | $0.72 | $2,160 | No expiry | [Enterprise 3,000 GB](https://bit.ly/9-Proxy) |
| 6,000 GB (Enterprise) | $0.70 | $4,200 | No expiry | [Enterprise 6,000 GB](https://bit.ly/9-Proxy) |
| 10,000 GB (Enterprise) | $0.68 | $6,800 | No expiry | [Enterprise 10,000 GB](https://bit.ly/9-Proxy) |

Two things are worth noting about how this ladder is built.

First, the price steps are front-loaded. Going from 5 GB to 100 GB cuts your per-GB rate in half. Going from 100 GB to 2,000 GB only halves it again. The steepest discount you'll ever get is the jump from the trial-sized pack to a real one.

Second, the Enterprise tiers stay at the same per-GB rate you'd have paid at 2,000 GB but remove the expiry clock entirely. That's the actual product there, not the three cents per gigabyte.

## The 180-day clock is the part people miss

Every GB plan except Enterprise carries 180 days of validity. Buy 5 GB to test the water, get pulled onto another project for seven months, come back, and the balance is gone.

This isn't unusual in the category, and 180 days is more generous than the monthly expiry most subscription-based providers enforce. But it does rewire how you should buy. If your workload is genuinely spiky, buying 50 GB that survives six months can beat buying 10 GB twice at a higher per-GB rate, even though you're paying more upfront.

For anyone running continuous infrastructure, the Enterprise tier's unlimited validity means bandwidth shared inside a team never expires. Up to five members can draw on the same pool, with per-member traffic controls and activity logs. If you're an agency buying traffic on behalf of clients, that structure removes the awkward "your gigabytes expired before the campaign started" conversation.

## Sticky or rotating, credentials or whitelist: what a gigabyte buys you

The GB model isn't just a billing difference. It changes what the proxies look like on your end.

**Sessions.** You choose rotating mode, where the exit IP changes per request or per session, or sticky mode, where it holds an IP for a configurable window. Both are set from the dashboard, not from a desktop app. GB-based proxies in 9Proxy's system don't require the client software that the IP-based product uses, so it works from cloud instances and headless environments without installing anything.

**Authentication.** Two options: username/password sub-users, or IP whitelisting where a device connects automatically once its IP is registered. Username/password is the more practical one for automation, since you can issue a sub-user per project and watch traffic per credential.

**Targeting.** Country, state, city, ZIP, and ISP level. For ad verification or localized price checks, ISP targeting is the piece that matters and the piece budget providers often skip.

**Network.** 9Proxy advertises 20M+ residential IPs across 90+ countries with HTTP/HTTPS and SOCKS5 support, and a claimed 99.95% uptime. On the geography count, that's below the big enterprise networks that advertise 100M+ or 195 countries. For US, UK, EU, and Southeast Asia work it's fine. If you need an obscure market, check coverage before you buy 500 GB you can't spend.

Self-reported uptime figures should be treated as marketing. Independent testing is a better signal, and the most detailed published test of 9Proxy ran 300 sequential requests through rotating residential IPs against a Cloudflare-protected e-commerce site: 293 passed, 5 hit CAPTCHAs, 2 were blocked, averaging 0.63 seconds per request. That's a 97.7% pass rate, and the same test through datacenter IPs produced a 34% block rate. One test isn't a benchmark suite, but the shape of the result is consistent with what residential routing is supposed to do.

Independent reviewers also flag two real drawbacks. There's no self-serve free trial on the website, so testing usually means asking support for a test balance, and coverage tops out at 90+ countries rather than the 195 some competitors list. Refund policy friction shows up in third-party review scores, so treat any purchase as a decision you'll live with.

## IP-based and bundle plans on the same account

GB traffic isn't the only thing on the menu. If your work splits between bandwidth-light rotation and long-lived sessions, 9Proxy sells the other two models on the same balance system.

| Plan type | What you get | Price | Notes |
| --- | --- | --- | --- |
| IP-based, small | 100 residential IPs | $24 | Unlimited bandwidth per active IP; unused IPs don't expire until activated |
| IP-based, mid | 500 residential IPs | $72 | Same model, lower per-IP cost |
| IP-based, 1,000 | 1,000 IPs + 500 bonus | $126 | Bonus IPs included |
| IP-based, large | 100,000 IPs | $2,300 | Volume tiers for resellers and agencies |
| IP-based, largest | 500,000 IPs | $8,625 | Wholesale pricing |
| Bundle Starter | 100 IPs + 5 GB | $30 | Both models in one purchase |
| Bundle Popular | 1,500 IPs + 50 GB | $180 | Mixed workloads |
| Bundle Pro | 5,000 IPs + 500 GB | $720 | High-volume combined use |

If you buy the Bundle Popular tier, you're paying $180 for the same resources that cost $96 as separate IP and GB purchases at those volume points — which is a reminder to run the arithmetic yourself rather than assuming bundles are always cheaper. Where bundles do help is procurement: one balance, one expiry window, one invoice.

Worth knowing: 9Proxy raised prices on IP-based and Bundle packages on June 1st, 2026, the first adjustment in the company's history. Bandwidth pricing was explicitly left unchanged, which is why the GB rates above still start at $3.00 and bottom out at $0.68.

## Discounts, trials, and testing before you commit

A few current routes to spending less:

- **Partner codes.** Geekflare publishes a limited-time 40% off code for the 50+5 GB plan, redeemable at checkout with the code `GEEKFLARE40`. Third-party promotional codes get retired without notice, so check it applies before you pay.
- **Payment-method bonuses.** Some payment routes reportedly carry an extra 5% discount or 5% bonus traffic. Which methods qualify varies, so confirm at checkout rather than assuming.
- **Free GB giveaways.** 9Proxy runs periodic promotions through its community channels, including free-1GB code drops and first-order coupons for GB customers. These come and go.
- **Test balance requests.** With no self-serve trial on the site, the practical path is asking support for test traffic, then running your own target against it.

The honest advice here has nothing to do with which code is live this week. Run your actual target against a small balance before buying volume. Proxy performance is target-specific, and a 97.7% success rate on someone else's e-commerce test says nothing about the specific site you need to scrape.

## How to keep your per-GB cost from creeping up

- Log your bandwidth per project for the first week. A surprising amount of proxy spend comes from one forgotten debug loop.
- Cap concurrency on retries. Failed requests still consume bytes.
- Use sticky sessions on sites that don't need rotation. Sticky isn't slower; it's often faster.
- Re-check whether you need full page renders. Most data extraction doesn't.
- Buy in the 100–200 GB band unless you have data proving you'll burn more. The rate improvement beyond 200 GB is 25 cents, and locking $800 into a 180-day window is a real risk for a project that might change scope next month.

## Quick answers

**Are there monthly subscriptions?** No. GB plans are prepaid balances. Nothing renews unless you buy more.

**Do unused gigabytes expire?** Yes, after 180 days on standard GB plans. Enterprise packages have no expiry.

**Is there a free trial?** Not self-serve on the website. Test traffic is usually arranged through support or community promotions.

**Can I do both per-GB and per-IP on one account?** Yes, and Bundle plans combine them in a single purchase.

**What happens if I run out mid-project?** You top up. Traffic is consumed from a balance, so there's no upgrade path to negotiate and no plan to migrate.

**Does 9Proxy charge for IP activation on GB plans?** No. The GB model bills data only, and endpoints are unlimited within your balance.

## Who should actually buy a pay-per-GB plan

If your workload is rotation-heavy, payload-light, and geographically spread, paying per gigabyte is the right structure, and 9Proxy's rate ladder from $3.00 down to $0.68 per gigabyte sits in the budget tier of the market rather than the premium one. The 180-day window is roomy for most project timelines, the lack of subscription commitment matters more than it sounds, and the 50+5 GB pack at $105 gives you enough traffic to run a real test rather than a toy one.

If you need long sessions on stable identities, or you're moving hundreds of gigabytes every month through a handful of IPs, don't buy gigabytes at all. The IP-based packages with unlimited bandwidth per active IP exist for exactly that shape of work, and they'll cost you less.

Either way, don't buy volume on day one. Grab a small balance, point it at the sites you actually care about, and let your own bandwidth numbers decide how much traffic you need.

👉 [Start with the 5 GB pack and measure your real usage first](https://bit.ly/9-Proxy)
