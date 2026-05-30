---
name: google-ads-expert-checklist
description: >
  Senior Google Ads practitioner's audit checklist — 27 specific checks grouped by category that
  go beyond surface metrics like CPA, CTR, and spend. Use whenever auditing a Google Ads account,
  running a weekly performance review, planning a quarterly structural review, or looking for
  issues beyond the obvious ones. Trigger on: "audit google ads", "account health", "what's wrong
  with my campaigns", "expert review", "senior review", "deep audit", "structural audit", "look
  beyond the surface", "what am I missing", "optimization gaps", or when another skill needs a
  reference for what a 20-year-practitioner would check.
---

# Google Ads Expert Checklist

Reference checklist of 27 things a senior Google Ads practitioner looks for beyond the basics. Organized by category so it can be used as a full audit pass or as a targeted lookup.

Originally built for a B2B SaaS account in a regulated industry. The structure is universal; calibrate the thresholds to your own account.

Every finding should be tagged Critical / High / Medium / Low based on your own priority rubric.

---

## How to use this skill

**As a full audit pass** — run all 27 items during a quarterly account audit or when onboarding a new account.

**As a targeted lookup** — when a weekly performance review or anomaly suggests a specific area, jump to the relevant category.

**As a reference during weekly optimizer runs** — items #5, #6, #9, #13, #15, and #24 (bidding health, change history, creative, disapprovals, QS trends) are worth checking every week.

**As a pre-write safety gate** — if you build a skill that mutates the account, item #15 (policy disapproval check) and item #16 (negative keyword conflicts) should run before any keyword or ad copy mutation.

---

## Category A — Campaign Structure & Architecture

### 1. PMax vs Search cannibalization

**Check:** are your brand terms appearing as search queries inside the PMax campaign instead of being captured by the Brand Search campaign?

**Why it matters:** PMax will aggressively absorb branded search traffic unless explicitly prevented. When it does, it claims conversions that would have cost cents on Brand Search and steals credit from cheaper branded clicks.

**How to check:** Pull PMax search terms (via GAQL or the Insights report). Scan for terms containing your brand or brand variants. If present, PMax is cannibalizing. Fix with brand exclusion lists on the PMax campaign (see item #21).

### 2. PMax channel-level spend distribution

**Check:** how is PMax spend split across Search, Display, YouTube, Discover, and Gmail channels inside the campaign?

**Why it matters:** PMax opacity hides where spend actually goes. Some campaigns effectively run as display-only; others are mostly search. This affects whether the creative set is being used and whether placements are appropriate for the audience.

**How to check:** PMax Insights → channel distribution report.

### 3. Campaign-type separation

**Check:** are Search, Display, YouTube, PMax, and Demand Gen in separate campaigns, or mixed?

**Why it matters:** Mixed types can't be optimized separately; budget fragments.

**Fix:** one campaign type per campaign. Move display/YouTube/Demand Gen into their own campaigns if they're inside a Search campaign.

### 4. Ad group theme coherence

**Check:** within a Search campaign, does each ad group target one tightly clustered intent? Or are keywords with different intents mixed together?

**Why it matters:** mixed-intent ad groups make ad copy impossible to tailor. Quality Score suffers.

**How to check:** 5–15 keywords per ad group, all on the same intent. Single Theme Ad Groups (STAGs) are the modern standard.

---

## Category B — Bidding Health

### 5. Smart Bidding learning state and strategy health

**Check:** are campaigns in Learning, Limited, or Eligible status? How long have they been in their current state?

**Why it matters:** campaigns stuck in Learning >14 days have a structural problem. Campaigns in Limited need the specific limitation identified (budget, bid, targeting).

**How to check:** Campaign settings → Bid Strategy status, or GAQL `campaign.bidding_strategy_system_status`.

### 6. tCPA / tROAS target vs actual performance

**Check:** is the target within a reasonable band of trailing 30-day actual performance?

**Why it matters:** target set >20% more aggressive than actual → constrains delivery. Target set >30% more conservative → leaves performance on the table.

**How to check:** compare target to trailing 30-day actual and trailing 90-day actual. Flag the deltas.

**Bidding strategy by monthly conversion volume:**

| Monthly conversions | Appropriate strategy |
|---|---|
| <15 | Max Conversions or Manual CPC with bid cap |
| 15–29 | Smart Bidding functional but unstable; don't trust short-term signals |
| 30–49 | Target CPA / Target ROAS eligible |
| 50+ | Stable Smart Bidding; reliable targets |

### 7. Conversion lag analysis

**Check:** how many days elapse between ad click and the conversion event firing?

**Why it matters:** if conversion lag is long (weeks) and you're evaluating 7-day performance, you're evaluating on incomplete data. B2B sales cycles are long enough that this is usually a real factor.

**How to check:** GAQL `segments.conversion_lag_bucket` or the Attribution report.

### 8. Budget constraint analysis

**Check:** which campaigns hit their daily cap before end of day (Impression Share Lost to Budget)?

**Why it matters:** capped campaigns are leaving impressions on the table. Differentiate budget-constrained (raise budget) from rank-constrained (improve QS / bid).

**How to check:** `metrics.search_budget_lost_impression_share` and `metrics.search_rank_lost_impression_share`.

### 9. Change history correlation

**Check:** did recent changes (last 60 days) correlate with performance shifts?

**Why it matters:** surfaces the "bidding spiral" pattern — successive target tightenings without improvement. Also surfaces unintended side effects of otherwise-reasonable changes.

**How to check:** GAQL `change_event` for last 60 days, correlated against performance windows 14 days before and after each change. Run this FIRST before interpreting any performance data.

---

## Category C — Audience Quality

### 10. Customer Match list health

**Check:** size (≥1,000 min, 5,000+ recommended), match rate (>50% for email), and recency (updated within 30 days).

**Why it matters:** under-spec'd lists can't be used for Lookalikes, match audiences, or exclusions. Stale lists miss new customers and keep churned ones.

### 11. Audience signal effectiveness in PMax

**Check:** are PMax audience signals actually helping the algorithm? Or are they too weak / too broad to guide optimization?

**Why it matters:** weak signals waste PMax's initial learning phase.

**How to check:** PMax Insights → Audience report. Compare signal-influenced performance to broad.

### 12. Exclusion hygiene

**Check:** three specific exclusions:
- **Existing customers excluded from prospecting** (the most expensive leak — paying to serve ads to users already paying you)
- **Recent converters excluded from conversion campaigns** (7–30 day window, prevents paying to re-convert)
- **In-pipeline leads excluded from cold lead-gen** (MQLs shouldn't be retargeted as cold)

**Why it matters:** direct wasted spend.

**How to check:** Campaign exclusions → Customer lists. Verify all three are applied.

---

## Category D — Creative & Copy

### 13. RSA combination serving patterns

**Check:** which headlines and descriptions are actually serving in which combinations? What's the ad strength distribution?

**Why it matters:** the 15 headlines and 4 descriptions you write are not all served equally. Google's engine picks. Some never serve. Some combinations work; others don't. Seeing the pattern informs the next copy refresh.

**How to check:** Ad asset details report, GAQL `segments.asset_performance_label`.

### 14. PMax asset performance labels (BEST / GOOD / LOW)

**Check:** what's the distribution of BEST/GOOD/LOW labels across headlines, images, and videos in each PMax asset group?

**Why it matters:** PMax gives each asset a quality label. A group that's mostly LOW is underperforming despite the campaign looking fine at the top level. Replace LOW assets first.

**How to check:** Asset group detail, or GAQL `asset.performance_label`.

### 15. Policy disapprovals blocking impressions on active ads

**Check:** are any ads in enabled campaigns marked DISAPPROVED?

**Why it matters:** a disapproved ad in a live campaign looks live but serves nothing. Easy to miss because the campaign aggregates look normal.

**How to check:** GAQL `ad_group_ad.status = ENABLED AND ad_group_ad.policy_summary.approval_status = DISAPPROVED`, or the Ads & assets → Ads view with status filter.

**Higher stakes for regulated categories** (healthcare, financial services, restricted industries) — disapproval risk is higher than a generic account. Worth a daily script if your category is restricted.

---

## Category E — Search Terms & Keywords

### 16. Negative keyword conflicts

**Check:** are any positive keywords being blocked by a negative keyword in the same account?

**Why it matters:** easy to create — a broad-match negative in one campaign can block an exact-match positive in another. Silent loss of traffic.

**How to check:** GAQL cross-reference between keyword and negative keyword criteria, or Google Ads Recommendations tab.

### 17. Search Terms cross-campaign cannibalization

**Check:** is the same search term appearing in 2+ campaigns' search terms reports?

**Why it matters:** you're bidding against yourself; driving up auction prices for your own traffic.

**How to check:** pull Search Terms Report account-wide, flag any term appearing in multiple campaigns. Most commonly PMax vs Search.

---

## Category F — Time & Geography

### 18. Ad schedule vs actual conversion times

**Check:** when do conversions actually happen by hour and day?

**Why it matters:** if conversions concentrate on weekday business hours (typical for B2B), weekend / overnight spend may be lower-efficiency.

**How to check:** GAQL `segments.day_of_week` and `segments.hour` joined to conversion metrics.

### 19. Geographic bid adjustments

**Check:** are there geo-level patterns (state, metro) where performance materially differs and bid adjustments could compound the advantage?

**Why it matters:** even within "US-only," some metros convert 2–3× better. Bid modifiers capture the premium.

**How to check:** Location performance report segmented by state or metro, with conversions + CPA.

---

## Category G — PMax-Specific

### 20. Search theme overlap across PMax campaigns

**Check:** if multiple PMax campaigns exist, are their search themes overlapping (competing for the same queries)?

**Why it matters:** PMax campaigns with overlapping themes bid against each other through PMax's internal allocation.

### 21. Brand exclusion lists in PMax

**Check:** does each PMax campaign have a brand exclusion list that prevents it from serving on queries for your brand?

**Why it matters:** this is the mechanism for preventing item #1. Brand terms go in PMax's brand exclusion list (negative keyword list).

**How to check:** PMax campaign settings → Brand exclusions.

### 22. Placement exclusion opportunities (Display/YouTube in PMax)

**Check:** are there placements (URLs, apps, YouTube channels) where PMax spend is going that should be excluded?

**Why it matters:** PMax's display/video spend can leak to irrelevant or low-quality placements if not actively managed.

**How to check:** PMax Insights → Placements report. Review for apps, gaming sites, Made-For-Kids YouTube content, or anything off-ICP.

---

## Category H — Attribution & Measurement

### 23. Conversion value rules usage

**Check:** are conversion value rules in use (adjusting conversion values by geo, audience, device)?

**Why it matters:** can be used to prioritize high-value cohorts or correct for value-tracking limitations.

**How to check:** `conversion_value_rule` resource via GAQL.

### 24. QS trending over time

**Check:** is Quality Score improving, stable, or degrading on the top-spend keywords over the last 90 days?

**Why it matters:** point-in-time QS hides trends. A keyword at QS 7 today could be drifting down; a keyword at QS 5 could be climbing. Trend matters for future CPC.

**How to check:** historical `keyword_view.metrics.historical_quality_score` over 90 days.

### 25. Seasonality adjustments and data exclusions

**Check:** if there have been atypical events (outages, holidays, unusual promos), has a data exclusion been applied so Smart Bidding doesn't over-weight them?

**Why it matters:** without exclusions, one bad week trains the algorithm on noise.

**How to check:** Tools → Bid strategies → Advanced controls → Data exclusions.

---

## Category I — Competitive & Growth

### 26. Active experiments and statistical significance

**Check:** are there active Campaign Experiments or Ad Variations? Have they reached significance?

**Why it matters:** experiments left running past significance waste budget. Experiments stopped too early give false readings.

**How to check:** Experiments section in Google Ads UI, or `experiment` resource in GAQL.

### 27. Bid simulator scaling opportunities

**Check:** does the bid simulator show meaningful incremental volume available if bid or budget were increased?

**Why it matters:** quantifies whether there's headroom to scale, or whether you're already capturing most of the available market.

**How to check:** Bid simulator data per campaign (available when sufficient data exists).

---

## Quick Reference — All 27 Items

| # | Item | Category |
|---|---|---|
| 1 | PMax vs Search cannibalization | Structure |
| 2 | PMax channel-level spend distribution | Structure |
| 3 | Campaign-type separation | Structure |
| 4 | Ad group theme coherence | Structure |
| 5 | Smart Bidding learning state | Bidding |
| 6 | tCPA/tROAS target vs actual | Bidding |
| 7 | Conversion lag analysis | Bidding |
| 8 | Budget constraint analysis | Bidding |
| 9 | Change history correlation | Bidding |
| 10 | Customer Match list health | Audience |
| 11 | PMax audience signal effectiveness | Audience |
| 12 | Exclusion hygiene (3-part) | Audience |
| 13 | RSA combination serving patterns | Creative |
| 14 | PMax asset performance labels | Creative |
| 15 | Policy disapprovals blocking impressions | Creative |
| 16 | Negative keyword conflicts | Keywords |
| 17 | Search Terms cross-campaign cannibalization | Keywords |
| 18 | Ad schedule vs actual conversion times | Time/Geo |
| 19 | Geographic bid adjustments | Time/Geo |
| 20 | Search theme overlap across PMax campaigns | PMax |
| 21 | Brand exclusion lists in PMax | PMax |
| 22 | Placement exclusion opportunities | PMax |
| 23 | Conversion value rules usage | Measurement |
| 24 | QS trending over time | Measurement |
| 25 | Seasonality adjustments | Measurement |
| 26 | Active experiments and significance | Growth |
| 27 | Bid simulator scaling opportunities | Growth |

---

## How to use this in Claude

Drop this file into your project skills folder. Use it three ways:

1. **Weekly review companion.** Tell Claude *"run the weekly review and consult the expert checklist for items 5, 6, 9, 13, 15, and 24."* Those six are the ones that matter most for weekly optimization.

2. **Quarterly account audit.** Tell Claude *"run a full account audit using all 27 items in the expert checklist."* Expect a long output — pair it with a priority rubric so the recommendations come back ranked.

3. **Targeted lookup.** Ask Claude *"check items 1, 17, and 21 — I think PMax is cannibalizing my Search campaign."* The category structure is designed for this.

If the checklist is useful, calibrate it to your own account: add items for your specific category (regulated industries especially), drop items that don't apply to your campaign types, and tune the thresholds in items #5, #6, and #12 to your conversion volume.
