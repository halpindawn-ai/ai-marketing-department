# Paid Acquisition AI Employee — build order

A sequencing template for building a paid acquisition AI employee one touchpoint at a time. Each layer reveals the gap the next layer fills. The order matters more than the destination.

This is the order I actually built mine in. The role spec I wrote up front predicted very little of it.

---

## How to use this

Pick the first layer. Build it. Run it for one or two cadences. The output of that layer will tell you what to build next. Resist building three layers in parallel — the value of the sequence is that each layer informs the next.

Drop this template into Claude and say *"help me build layer 1 for [your company]"* and it will interview you for the specifics.

---

## The layers, in order

### Layer 1 — Scorecard reporting

**What it does.** Pulls weekly ad spend, lead volume, and pipeline data into the reporting format you already maintain by hand.

**Cadence.** Weekly. Monday morning is the natural slot.

**Why this is first.** Boring on purpose. The job is to give yourself back the hours you were spending in spreadsheets so you can use them to build the next layer. It also forces you to wire up data access — once Claude can read your ads data and your CRM data, everything downstream is easier.

**What you need.** Read access to your ads platform data (Google Ads, Meta, LinkedIn — whichever you run) and read access to your CRM pipeline data. A target sheet or doc to write into.

**Gap this layer surfaces.** The data is now sitting in a structured format every week. The natural next question is *"what should we do about it?"*

---

### Layer 2 — Optimization recommendations

**What it does.** Reads the same data the scorecard reads and outputs a prioritized list of optimization moves — bid changes, budget shifts, campaigns to pause, ad groups to test.

**Cadence.** Weekly. Runs after the scorecard.

**Why this is second.** The scorecard tells you what happened. The optimizer tells you what to do. You need the scorecard first because the optimizer reads the same data plumbing.

**What you need.** A clear definition of what "good" looks like (CPA target, ROAS target, lead-volume floor) and a priority rubric (Critical / High / Medium / Low works fine). The rubric is what makes the recommendations actionable instead of overwhelming.

**Gap this layer surfaces.** The optimizer will keep recommending bid changes on campaigns whose landing pages are broken. You'll notice you can't actually action half the recommendations because the LP is the bottleneck.

---

### Layer 3 — Landing page checks

**What it does.** Audits each campaign's destination URL for the things that affect Quality Score / Ad Rank — message match between ad and page, keyword presence, page speed, trust signals, conversion path clarity.

**Cadence.** On-demand for new campaigns; quarterly sweep for existing ones.

**Why this is third.** The optimizer's recommendations don't land unless the LPs they point at are healthy. Adding the LP audit closes that loop.

**What you need.** Browser access (a headless browser tool or equivalent) and a clear definition of what the audit should check. Steal the Quality Score components from Google's documentation — they're the most universally agreed-on rubric.

**Gap this layer surfaces.** Now you can action LP fixes, but the optimizer keeps recommending bid lowering on search terms that should never have matched in the first place.

---

### Layer 4 — Negative keyword review

**What it does.** Reads the search terms report each week, classifies waste (irrelevant industry, wrong intent, brand of competitor, etc.), and packages the negatives for bulk upload.

**Cadence.** Weekly. Runs after the optimizer.

**Why this is fourth.** Negatives are the cleanup layer. Without them, the optimizer keeps flagging the same waste week after week and you keep manually working around it. Once negatives are running, the optimizer's recommendations get cleaner because the data is cleaner.

**What you need.** A taxonomy of negative categories specific to your business (industry-mismatch, intent-mismatch, competitor brand, etc.) and a Google Ads Editor-ready CSV template for the bulk upload.

**Gap this layer surfaces.** Weekly is too slow. By the time Monday's negative keyword review runs, mid-week issues have been bleeding spend for days.

---

### Layer 5 — Account monitoring

**What it does.** Runs daily checks against the ad account and alerts only when something trips a threshold — ad disapprovals, pacing anomalies, sudden quality score drops, broken landing pages, conversion tracking gaps.

**Cadence.** Daily. Silent unless tripped. (This is the key design choice — alert fatigue kills monitoring systems faster than anything else.)

**Why this is fifth.** Cadence-based reporting only catches issues once a week. Account-level monitoring catches mid-week disasters before they snowball. Build this after the weekly stack is solid, not before, or the alerts will fight your weekly workflow.

**What you need.** Either platform-native scripts (Google Ads Scripts for Google, similar primitives on other platforms) or an external runner that polls the API. A clear threshold for each check. An alert destination (Slack or email).

**Gap this layer surfaces.** You're now making more changes than you can remember. The next time you want to know why a campaign performed differently in week 4 than week 2, you can't reconstruct what changed.

---

### Layer 6 — Weekly changelog

**What it does.** Writes a structured weekly record of every change made to the ad account — what changed, why, what experiment it ties to, what the expected impact was — and publishes it to your team's docs site.

**Cadence.** Weekly. Last thing every Monday.

**Why this is sixth and not earlier.** The changelog only earns its keep once you're making enough changes that you'd otherwise lose track. Build it any earlier and you'll be documenting trivial weeks.

**What you need.** A target docs surface (Confluence, Notion, a Google Doc — anything searchable). A consistent format with five fields per entry: what changed, why, ticket/experiment ID, expected impact, actual impact (filled in the following week).

**Gap this layer surfaces.** You now have memory and recommendations and monitoring. The remaining gap is conversation — you can't ask the system anything ad hoc. Push-only is half a product. The next layer to build is a Q&A surface, but that's where my own build is right now, so you can have my best guess and not my finished pattern.

---

## What's not in this list

A few touchpoints I've intentionally left for later layers, in rough order of when I think they should come in:

- **Ad copy generation and refresh.** Useful once layers 1–4 are stable. Doing it earlier produces volume without feedback.
- **Campaign creation from a brief.** Useful once you've decided your campaign template. Hard to template until you've actually built a few.
- **Quarterly account audit.** Useful once you have 90 days of change history to audit against.
- **Competitive intelligence.** Useful once your own account is healthy. Studying competitors before fixing your own setup is a distraction.
- **Q&A surface (Slack bot or similar).** Useful from day one, but harder to build than any of layers 1–6. Build it when push-only starts failing you.

Order is opinionated. Mileage will vary.

---

## What to do when you're stuck

If a layer is taking more than one or two cadences to settle, the gap is probably one of these:

- **Data access.** The layer can't read what it needs. Fix the plumbing first.
- **No clear definition of "good."** The layer can produce output but can't say whether it's useful. Write the rubric.
- **Output destination unclear.** You know what the layer should produce but not where it should land. Pick a destination (Slack, sheet, doc) and commit.

When in doubt, end the build session by asking Claude *"should we make a skill from this?"* — the rule from Issue #2. If yes, the layer's role spec gets a permanent home.
