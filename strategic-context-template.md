# Strategic Context Template

A markdown file that codifies the "why" behind your function. The goals you're trying to hit, the constraints you have to work within, the team you have, and the decision frameworks you use. Load it as a Claude Code reference skill so every AI employee in your stack acts in line with your strategic reality, not a generic version of it.

The point of this template is that AI without strategic context defaults to averages. With it, every decision the AI makes is informed by what actually matters at your company this quarter.

Fill in the bracketed placeholders with your own answers. The examples below each section are illustrative. Replace them with your own when you have your own.

---

## How to use it

**As a Claude Code skill.** Save this file as `strategic-context/SKILL.md` in your skills folder. Have it auto-load before any planning, prioritization, or decision-making task. Reference it from operator skills that need to know what "good" looks like for your function.

**As a prompt instruction.** Paste below the request when you ask Claude for a recommendation, plan, or trade-off analysis. Add: *"Apply this strategic context to your answer."*

**As a self-check.** Read it before any major decision. If you can't articulate which goal or constraint this decision serves, you might be optimizing for the wrong thing.

---

## 1. Mission and positioning

What this function exists to do and how it fits into the larger business.

**Function:** `[The specific work this team owns]`

**Mission:** `[What this function exists to accomplish, in one sentence]`

**How we fit into the business:** `[Where this function lives in the org and what it enables for other teams]`

*Illustrative example:*

> **Function:** Demand generation for a healthcare SaaS company.
>
> **Mission:** Generate qualified pipeline at an efficient CAC, prioritizing customers we can serve well over volume.
>
> **How we fit in:** Sits between product marketing (who defines who we sell to) and sales (who closes). We own the lead-to-MQL pipeline and the channels that produce it.

---

## 2. Goals

The specific outcomes this function is trying to hit. Be concrete. "Grow pipeline" is not a goal. "Generate $3M in attributed pipeline this quarter, with a CAC below $X" is a goal.

**This quarter:**
- `[Goal 1]`: `[target, deadline]`
- `[Goal 2]`: `[target, deadline]`

**This year:**
- `[Goal 1]`: `[target]`
- `[Goal 2]`: `[target]`

*Illustrative example:*

> This quarter:
> - $1.2M in attributed pipeline from paid acquisition by end of Q2
> - 15 new published research assets distributed across owned channels
> - Lifecycle nurture sequences live for all 6 lead sources
>
> This year:
> - 4 published demand gen reports
> - Full AI marketing team at Level 2 maturity or above
> - Pipeline-to-revenue conversion rate up 20% over last year

---

## 3. Constraints

The things you can't do or can't afford to ignore. Regulatory, resource, technical, brand. These are the guardrails the AI needs to respect.

**Regulatory:**
- `[Constraint]`: `[what it means in practice]`

**Resource:**
- `[Constraint]`: `[what it means in practice]`

**Technical:**
- `[Constraint]`: `[what it means in practice]`

**Brand:**
- `[Constraint]`: `[what it means in practice]`

*Illustrative example:*

> Regulatory:
> - HIPAA compliance is non-negotiable in every customer-facing system
> - All vendor contracts require a signed BAA before any PHI flows
>
> Resource:
> - Headcount is fixed for the year; new work has to come from automation or reprioritization
> - Marketing budget for paid is capped at $X per quarter
>
> Technical:
> - HubSpot is the source of truth for pipeline data
> - Google Ads is the only paid channel currently active
> - All AI skills live in Claude Code, not standalone agents
>
> Brand:
> - Never make promises in marketing that the product can't back up
> - Competitor stats and quotes require approval before external citation

---

## 4. Team structure

Who does what. The human team and the AI team, side by side. Helps the AI know who to surface decisions to and what handoffs to respect.

**Human team:**
- `[Role]`: `[name or alias, what they own]`
- `[Role]`: `[name or alias, what they own]`

**AI team (employees with skills shipping):**
- `[Employee 1]`: `[scope]`
- `[Employee 2]`: `[scope]`

**Cross-functional dependencies:**
- `[Function]`: `[what they own that affects us]`

*Illustrative example:*

> Human team:
> - Demand gen manager (me): owns the function, approves all launches
> - VP marketing: approves budget decisions, signs off on strategic shifts
> - PMM lead: owns positioning, ICP, and the messaging frameworks downstream marketing reads from
>
> AI team (active):
> - Paid Acquisition Manager: pipeline generation from paid ads end to end
> - Campaign & Content Manager: content production and distribution across channels
> - Research & Insights Manager: original research and the shared brain
> - Reporting & Analytics Manager: marketing performance reporting
> - Lifecycle & Nurture Manager: email lifecycle and list health
>
> Cross-functional dependencies:
> - Sales: owns MQL-to-close. We hand off at MQL; they own from there.
> - Product marketing: owns positioning and ICP. We pull from their work.
> - Customer success: voice-of-customer feedback informs our content.

---

## 5. AI infrastructure

What's been built, what's in flight, what's gap. Helps the AI know what to suggest vs. what already exists.

**Reference skills (the shared brain):**
- `[Skill name]`: `[what it stores]`

**Operator skills (recurring workflows):**
- `[Skill name]`: `[what it does]`

**Expert skills (judgment work):**
- `[Skill name]`: `[what it analyzes]`

**Known gaps:**
- `[Gap]`: `[what would unlock it]`

*Illustrative example:*

> Reference skills:
> - Brand guidelines, writing standards, ICP definitions, AI writing detector, strategic context (this file), research catalog, VoC database
>
> Operator skills:
> - Paid Acquisition Manager has 19 skills covering campaign launch, weekly reporting, continuous optimization
> - Campaign & Content Manager has 27 skills covering blog, social, landing pages, webinars
>
> Expert skills:
> - AI writing detector, GTM lead analysis, Google Ads optimizer
>
> Known gaps:
> - Multi-touch attribution: still last-touch only via Sheets formulas
> - Nurture sequence builder: still hand-built per sequence

---

## 6. Decision frameworks

How you choose between options. Encoded so the AI can apply the same logic you would, not whatever logic seems reasonable in the moment.

**Framework 1:** `[Name of decision]`

`[The rubric or rule you apply]`

**Framework 2:** `[Name of decision]`

`[The rubric or rule you apply]`

*Illustrative example:*

> **Framework: What becomes a skill?**
>
> At the end of every build or brainstorm session, ask Claude: "Should we make a skill from this?" If the answer is yes, the skill goes into an employee's spec or directly into the shared brain. If no, move on.
>
> **Framework: When to increase ad spend?**
>
> Never increase budget on a campaign until it has produced confirmed closed-won revenue. Volume goals come second to attribution proof.
>
> **Framework: How to choose between two content topics?**
>
> Both have to clear ICP relevance, source-availability for the claim, and channel fit. If both clear, choose the one that compounds (more reusable in other formats).

---

## 7. Current priorities

What you're working on right now. Updated quarterly or whenever the focus shifts.

**Top three this quarter:**
1. `[Priority 1]`: `[why now]`
2. `[Priority 2]`: `[why now]`
3. `[Priority 3]`: `[why now]`

**What we're not doing right now (and why):**
- `[Thing we're not doing]`: `[why we're holding off]`

*Illustrative example:*

> Top three this quarter:
> 1. Build the nurture sequence builder skill: biggest gap blocking Lifecycle & Nurture Manager from Level 2
> 2. Close multi-touch attribution: every other reporting decision depends on this
> 3. Ship four new demand gen reports: research output drives every other channel
>
> What we're not doing right now:
> - Standing up a paid social presence: organic LinkedIn is working; paid social hasn't proven out for our ICP yet
> - Building an SDR-facing AI employee: SDR motion is too new to know what to automate

---

## 8. Out of scope

The work that explicitly does not belong to this function. Helps the AI not drift into adjacent territory and helps it route requests correctly.

`[Work type]`: `[why it's out of scope]` `[who owns it instead]`

*Illustrative example:*

> - Sales enablement assets: SDR/AE leadership owns this. We provide source content; they own the framing for sales conversations.
> - Customer marketing: post-purchase comms are owned by customer success. We hand off at MQL.
> - PR strategy: communications team owns. We provide research hooks; they own outreach and placement.

---

## What good looks like for your function

Once you have a few months of working with this template, come back and write a paragraph here. The paragraph should describe what "good strategic discipline" looks like in your function. Not abstract; the actual texture of decisions made well.

`[Your description of what good looks like]`

---

*This template is shared as part of [The AI Marketing Department](https://theaimarketingdepartment.substack.com), a Substack about building an AI demand gen team in public.*
