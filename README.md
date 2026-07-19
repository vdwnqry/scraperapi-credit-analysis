# ScraperAPI Free Trial Complete Guide: How to Start Scraping for Free, What You Actually Get, Which Plan Makes Sense — Plus Full Pricing Breakdown and the Credit Math Nobody Tells You About

So you found ScraperAPI, and now you want to know if the free trial is worth your time before putting a card anywhere near it. Smart move. Let's walk through exactly what you get, how to actually use it, where the gotchas are hiding, and whether the paid plans make sense once your 7 days are up.

---

## What the ScraperAPI Free Trial Actually Gives You

Here's the thing most review articles bury in paragraph six: ScraperAPI doesn't just have a free trial — it has **two distinct free offerings**, and confusing them is an easy way to mismanage your testing.

**The 7-Day Free Trial**: When you first sign up, you get 5,000 API credits to burn through in the first week. No credit card, no sales call, no commitment. This is the trial period where you test the API against your actual target URLs at something resembling real scale.

**The Permanent Free Plan**: After those 7 days, even if you don't upgrade, your account stays alive on the free plan — which gives you 1,000 credits per month, forever, with up to 5 concurrent connections. It's not a lot, but it's enough to keep a side project alive, run occasional tests, or decide you want to scale up.

> 👉 [Claim your free 5,000 API credits — no credit card required](https://www.scraperapi.com/?fp_ref=coupons)

The signup itself takes under two minutes. Email, password, done. You land in a dashboard with your API key sitting right there, plus a credit counter showing your 5,000 trial credits. From that point, you're one API call away from scraping your first page.

---

## How to Use the Free Trial: From Sign-Up to First Request

A lot of people sign up, poke around the dashboard, and then never actually make a request because it feels more complex than it is. It isn't. Here's the actual flow.

**Step 1: Create your account.** Head to the ScraperAPI sign-up page and register with just an email. No credit card, no phone number, no corporate questionnaire.

**Step 2: Grab your API key.** It's displayed immediately in your dashboard. Copy it somewhere.

**Step 3: Make your first request.** The simplest possible call looks like this — just replace `YOUR_API_KEY` with your actual key and point it at any URL you want to scrape:


https://api.scraperapi.com?api_key=YOUR_API_KEY&url=https://example.com


You can paste that directly into a browser to test. Or use it with Python's `requests` library, curl, Postman, or whatever tool you already use. ScraperAPI handles proxy rotation, CAPTCHA solving, and JavaScript rendering on their end — you just receive HTML back.

**Step 4: Enable JavaScript rendering if you need it.** For JavaScript-heavy sites (single-page apps, sites that load content dynamically), add `&render=true` to your request. More on why this matters for your credit balance in a minute.

**Step 5: Monitor usage in the dashboard.** The analytics panel shows credit consumption, success rates, average latency, and which domains you've been hitting. Keep an eye on it — there are no proactive alerts when you're running low.

---

## The Credit System: Read This Before You Burn Through Your Trial Credits in Two Days

This is the part that surprises almost everyone on the free trial. You have 5,000 credits. You start scraping. Three days later, the counter reads zero. What happened?

ScraperAPI uses a credit multiplier system, and the multipliers are not small. Here's the actual breakdown:

**Domain-based costs (these are automatic — you can't opt out):**

| Domain Type | Credits Per Request |
|---|---|
| Normal websites (blogs, news, etc.) | 1 |
| Amazon and e-commerce | 5 |
| Google, Bing (SERP) | 25 |
| LinkedIn | 30 |

**Parameter-based costs (these you control):**

| Parameter | Extra Credits Added |
|---|---|
| `render=true` (JavaScript rendering) | +10 |
| `screenshot=true` | +10 |
| `premium=true` (residential proxy) | +10 |
| `ultra_premium=true` | +30 |
| `premium=true` + `render=true` combined | +25 total (not +20) |
| `ultra_premium=true` + `render=true` combined | +75 total (not +40) |

That last row is the kicker. When you combine parameters, the cost is *not* additive — it's higher than the sum of the parts. Combined ultra-premium plus JavaScript rendering costs 75 extra credits per request, not 40.

Anti-bot bypass costs also apply automatically — Cloudflare, DataDome, and PerimeterX each add +10 credits when detected, and you don't choose this; the system applies it when it needs to.

**A practical example:** If you're scraping Amazon product pages with JavaScript rendering enabled, each request costs 5 (Amazon multiplier) + 10 (render) = 15 credits. Your 5,000 free trial credits cover exactly 333 pages. Plan around that reality, not the headline number.

> **Pro tip for your free trial:** Start with `render=false` unless you confirm the site actually needs JavaScript. For many static sites, you'll get full HTML without the rendering overhead. Use the API Playground in your dashboard to check what any specific URL will cost before running batch jobs.

---

## Full ScraperAPI Plan Comparison Table

Once the free trial window closes, here's what your upgrade options look like. All paid plans include JavaScript rendering, full crawler access, geotargeting (with some restrictions noted), and 7-day money-back guarantee.

| Plan | Monthly Price | Annual Price (per mo) | API Credits | Concurrent Threads | Geotargeting | Purchase |
|---|---|---|---|---|---|---|
| **Free** | $0 | $0 | 1,000/month | 5 | No |  [Get Free Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Hobby** | $49/mo | $44.10/mo | 100,000/month | 20 | US & EU only |  [Start Hobby Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Startup** | $149/mo | $134.10/mo | 1,000,000/month | 50 | US & EU only |  [Start Startup Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Business** | $299/mo | $269.10/mo | 3,000,000/month | 100 | 50+ countries |  [Start Business Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Scaling** | $475/mo | $427.50/mo | 5,000,000/month | 200 | 50+ countries |  [Start Scaling Plan](https://www.scraperapi.com/?fp_ref=coupons) |
| **Enterprise** | Custom | Custom | 5M+/month | 200+ | Full |  [Contact Sales](https://www.scraperapi.com/?fp_ref=coupons) |

**A few things worth noting before you pick a tier:**

- The **annual discount** is 10% across all plans. If you already know you'll stick around, locking in the annual rate on day one makes sense.
- **Geotargeting is gated.** If your work requires scraping from specific countries outside the US and EU, you need Business or above. There's no workaround on lower tiers.
- **Pay-As-You-Go (PAYG)** is only available on Scaling, Professional, and Enterprise plans. If you're on Hobby, Startup, or Business and exhaust your credits before the month ends, you're cut off until your next billing date — upgrading is your only option.
- **Credits don't roll over.** Unused credits expire at the end of each billing cycle. If you consistently underuse your plan, consider dropping a tier.
- The **Education plan** is a separate track for academic researchers — apply directly through ScraperAPI's website.

---

## Where ScraperAPI Performs Well (And Where It Doesn't)

The ScraperAPI free trial is a good testing environment precisely because performance varies *a lot* by target site. Here's what independent benchmarks show:

**Strong performers:**

- **Zillow**: 100% success rate in recent benchmarks — their best site by far
- **Amazon**: 98% — solid, and the structured data endpoints return clean parsed JSON
- **Etsy**: 99%
- **Walmart**: 93%
- **LinkedIn**: 95% (though at 30 credits per request, costs add up quickly)

**Weak or non-functional:**

- **Instagram**: 0% success rate
- **Twitter/X**: 0%
- **Booking.com**: 0%
- **Realtor.com**: 12%

The honest read is that ScraperAPI is excellent for e-commerce and real estate data, reasonable for SERP scraping, and not the tool for social media platforms. If your primary targets are in the failing category, find that out during your free trial rather than after committing to a paid plan.

One behavioral quirk worth knowing: ScraperAPI applies a **10-minute forced result cache** on difficult targets. If you're scraping time-sensitive pricing data and need fresh results every few minutes, you may get stale data. Test this on your specific targets during the trial window.

---

## The Structured Data Endpoints: ScraperAPI's Hidden Gem

Buried under the main API documentation is a feature set that deserves more attention: **Structured Data Endpoints (SDEs)** for 18 specific data types across five platforms.

Instead of getting raw HTML that you then need to parse yourself, SDEs return clean JSON directly:

- **Amazon** (3 endpoints): Product details by ASIN (18+ fields including price, ratings, reviews, BSR, images, seller info), search results, competitor offers — across 21 regional marketplaces
- **Google** (5 endpoints): SERP results, Shopping, Maps, News, Jobs
- **Walmart** (4 endpoints): Product, Search, Category, Reviews
- **eBay** (2 endpoints): Product, Search
- **Redfin** (4 endpoints): Search, Rental Properties, For Sale, Agent Details

These are available on all plans including the free tier, which means you can test them during your ScraperAPI free trial. For teams who don't want to write and maintain their own HTML parsers, this is a significant time-saver. Amazon requests cost 5 credits via SDE, the same as a raw Amazon request — you're getting the parsing work done for free at that rate.

---

## Who Should Actually Use ScraperAPI?

After going through everything, here's the honest breakdown:

**ScraperAPI makes sense if:**
- You have existing scraper code and need a reliable proxy/rendering layer dropped in front of it
- Your primary targets are e-commerce (Amazon, Walmart, Etsy) or real estate (Zillow)
- You're scraping under 500K pages per month at your current scale
- Your team has engineering capacity to handle parsing, storage, and scheduling on your end
- You want a quick proof-of-concept without infrastructure setup

**ScraperAPI is probably not the right fit if:**
- Your targets include social media (Instagram, Twitter/X, Booking.com have 0% success rates)
- You need to scrape sites behind login walls — ScraperAPI's terms of service explicitly forbid this
- You need global geotargeting on a budget (Hobby and Startup plans are US/EU only)
- You're a non-technical user who doesn't want to write any code — the tool is built for developers
- You're scraping at enterprise scale (5M+ requests/month) with complex anti-bot requirements

For small and mid-scale developer projects, ScraperAPI hits a reasonable cost-to-reliability ratio. The 5,000-credit free trial gives you enough runway to genuinely test your specific use cases before committing money.

> 👉 [Start your ScraperAPI free trial — 5,000 credits, no credit card needed](https://www.scraperapi.com/?fp_ref=coupons)

---

## Billing Quirks Worth Knowing Before You Upgrade

A few things that have caught users off guard — better to know upfront:

**404 responses cost credits.** ScraperAPI charges for both successful (200) and not-found (404) responses. Only true failures (5xx errors) don't consume credits.

**Cancelling early costs you too.** If you cancel a request before the 70-second processing window completes, you're still charged.

**DataPipeline costs more than the regular API.** If you use ScraperAPI's no-code DataPipeline feature for scheduled scraping with webhook delivery, the credit costs are significantly higher — a basic normal request costs 6 credits in DataPipeline versus 1 credit via the standard API. Users who build no-code pipelines expecting standard credit rates discover the discrepancy quickly.

**No usage alerts.** The dashboard shows your consumption, but ScraperAPI doesn't send email or push notifications when you're approaching your credit limit. Set a calendar reminder to check manually during the first few weeks.

**Cancellation is straightforward.** You can cancel anytime from the billing page in your dashboard. No penalty, no retention calls. And there's a 7-day no-questions-asked refund policy if you pay for a plan and decide it's not working for you.

---

## How to Get the Most Out of Your Free Trial Credits

Five things that actually help:

1. **Check domain cost before running batch jobs.** Use the Domain Multiplier tool in your dashboard or the API Playground to see exactly what a specific URL costs before firing off 500 requests.

2. **Don't enable rendering by default.** Many sites serve full HTML without JavaScript rendering. Only turn on `render=true` after confirming the site actually loads content dynamically.

3. **Test your highest-priority targets first.** If you have three target domains, test all three in the first two days. Don't spend your credits perfecting the easiest domain while leaving your hardest target untested.

4. **Use sessions strategically.** The `session_number` parameter lets you stick to the same IP across multiple requests (for crawling multi-page workflows on one site). It doesn't cost extra credits — use it.

5. **Read the `sa-credit-cost` response header.** Every API response includes this header, showing exactly how many credits that specific request consumed. Use it to build accurate cost projections before scaling up.

---

## The Bottom Line on the ScraperAPI Free Trial

The ScraperAPI free trial is one of the more straightforward offers in the web scraping API space. No credit card, 5,000 credits on signup, another 1,000/month indefinitely on the free plan — you have real runway to test before spending anything.

The thing to watch is the credit math. The multiplier system means 5,000 credits isn't 5,000 pages once you factor in JavaScript rendering, premium proxies, or high-cost domains like Amazon or Google. Go in knowing that, test your specific targets during the trial window, and you'll have a clear picture of actual monthly costs before making any upgrade decision.

For developer teams building production data pipelines on well-supported targets (e-commerce, real estate, SERP), ScraperAPI is a solid workhorse. For everything else, the free trial will tell you what you need to know.

> 👉 [Create your free ScraperAPI account and claim 5,000 trial credits](https://www.scraperapi.com/?fp_ref=coupons)
