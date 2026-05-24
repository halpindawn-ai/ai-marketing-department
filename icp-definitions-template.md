# ICP Definitions Template

A markdown file that codifies who your company sells to, what they care about, and why they buy. Load it as a Claude Code reference skill so every content-producing and campaign-building skill in your stack writes for the right audience automatically.

**A note on origin:** the structure of this template is inspired by an ICP framework my product marketing manager (PMM) built for our team. She did the original thinking. I generalized it for sharing. If your company has a PMM team, they probably already have something like this. Pull from their work first; only build from scratch if nothing exists.

Fill in the bracketed placeholders. The illustrative examples below each section are intentionally generic; replace them with your own.

---

## How to use it

**As a Claude Code skill.** Save this file as `icp-definitions/SKILL.md` in your skills folder. Have it auto-load before any content draft, campaign brief, or audience targeting decision.

**As a prompt instruction.** Paste below the request when you ask Claude to write content for your audience or build a campaign. Add: *"Apply this ICP definition to the work."*

**As a self-check.** Read it before greenlighting a campaign or piece of content. If you can't name which persona it's for, the work probably won't land.

---

## 1. Primary ICP overview

The one-paragraph version. Who you sell to in plain language.

**Primary ICP:** `[Who you sell to in one sentence]`

**Why this ICP:** `[Why this customer profile is the best fit for what you sell]`

*Illustrative example:*

> **Primary ICP:** Mid-market healthcare organizations (50 to 500 employees) that handle PHI via email and need HIPAA compliant infrastructure without a dedicated IT team.
>
> **Why this ICP:** They have the regulatory pressure that creates urgency, the scale that justifies our pricing, and the resource constraints that make our "compliance without complexity" positioning resonate.

---

## 2. Firmographic criteria

The objective filters that define whether a company is in your ICP. The data points an SDR could verify in 30 seconds.

**Company size:** `[Employee range or revenue range]`

**Industry:** `[Specific industries, vertical, or sub-vertical]`

**Geography:** `[Where they operate]`

**Maturity stage:** `[Growth stage, year founded, public/private]`

**Tech stack indicators:** `[Technologies that signal they're a fit]`

*Illustrative example:*

> Company size: 50 to 500 employees, $10M to $100M annual revenue
>
> Industry: healthcare delivery (hospitals, ambulatory clinics, behavioral health, dental groups). Not pure healthtech SaaS (different needs).
>
> Geography: US only currently; expanding to Canada Q4
>
> Maturity stage: established practice or group, not pre-clinical startup
>
> Tech stack indicators: existing EHR (Epic, Athena, Cerner, eClinicalWorks). Microsoft 365 or Google Workspace for email.

---

## 3. Buyer personas

The specific roles inside an ICP company who buy, influence, and use the product. List 1 to 3. Be specific about responsibilities, success metrics, and what they care about.

### Persona 1: `[Title]`

**Owns:** `[What they're responsible for in the org]`

**Success metric:** `[How their performance is measured]`

**Reports to:** `[Who they report to, and what that person cares about]`

**What they care about:** `[The 2 to 3 things they think about most often]`

**What they don't care about:** `[Things you might assume they care about, that they actually don't]`

**Where they hang out:** `[Communities, publications, conferences, channels]`

### Persona 2: `[Title]`

`[Repeat the structure]`

*Illustrative example:*

> ### Persona 1: Practice administrator (mid-market healthcare org)
>
> **Owns:** day-to-day operations, vendor management, compliance program oversight.
>
> **Success metric:** clean audits, no breach incidents, vendor costs in line with budget.
>
> **Reports to:** practice owner or board. They care about regulatory exposure and operating margin.
>
> **What they care about:** avoiding regulatory penalties, keeping clinical staff productive, predictable monthly costs.
>
> **What they don't care about:** technical specifications, theoretical security features that don't show up in an audit.
>
> **Where they hang out:** MGMA, HFMA, state medical society newsletters, LinkedIn groups for practice administrators.

---

## 4. Buying triggers

The events that move a buyer from "maybe someday" to "I need this now." If you can spot these triggers, your content and campaigns become much more effective.

**Trigger 1:** `[Event]` `[why it creates urgency]`

**Trigger 2:** `[Event]` `[why it creates urgency]`

**Trigger 3:** `[Event]` `[why it creates urgency]`

*Illustrative example:*

> **Trigger 1: Failed audit or audit prep.** State or federal regulators flag a gap. Suddenly the line item that was deprioritized becomes urgent. Watch for healthcare news mentioning regulatory action.
>
> **Trigger 2: Breach at a peer.** When a comparable practice gets breached, every practice in their network re-evaluates. Public breach announcements in our space create a 3 to 6 week buying window.
>
> **Trigger 3: New executive joins.** Incoming compliance officer or practice administrator inherits the email stack and questions it. LinkedIn job changes are the signal.

---

## 5. Pain points

The problems your ICP has that your product solves. Be specific. "Compliance is hard" is too broad. "Audit prep eats 40 hours per year that should be billable" is useful.

**Pain 1:** `[Specific pain, in their language]`

**Pain 2:** `[Specific pain, in their language]`

**Pain 3:** `[Specific pain, in their language]`

*Illustrative example:*

> **Pain 1:** "Encryption requires patients to log into a portal to read their email. They don't, so they call instead. Compliance solved, productivity broken."
>
> **Pain 2:** "Audit prep eats 30 to 40 hours per year that should be patient-facing. The compliance team is the same team that handles HR."
>
> **Pain 3:** "Every vendor wants a BAA, but half of them push back when we send ours. We end up using vendors whose security we don't trust."

---

## 6. Common objections

The reasons buyers in your ICP don't buy, even when they should. Knowing these in advance lets your content pre-empt them.

**Objection 1:** `[The objection]`

**The reality:** `[Why this objection is wrong or overblown]`

**Objection 2:** `[The objection]`

**The reality:** `[Why this objection is wrong or overblown]`

*Illustrative example:*

> **Objection: "We already use [Microsoft/Google]'s built-in encryption. Isn't that enough?"**
>
> The reality: portal-based encryption forces patients to a separate login. Drop-off rates are 60 to 80%. Patients call or fax instead, defeating the workflow.
>
> **Objection: "Our IT team handles this."**
>
> The reality: most mid-market healthcare orgs have a 1 to 2 person IT team that's overloaded. Adding email security configuration on top of an EHR migration usually means it's deprioritized.

---

## 7. Anti-ICP

Companies that look like they fit but actually don't. Saying yes to anti-ICP customers is more expensive than saying no.

**Anti-ICP segment:** `[Description]`

**Why they look like a fit:** `[The superficial signals]`

**Why they aren't a fit:** `[The deeper reasons]`

*Illustrative example:*

> **Anti-ICP: Solo practitioners or under-10-person practices.**
>
> Why they look like a fit: they're in healthcare, they handle PHI, they need email security.
>
> Why they aren't a fit: their volume is too low to support our price point, their workflow needs differ from group practices, and our support model doesn't scale down well. Better routed to a partner solution.
>
> **Anti-ICP: Large hospital systems (1,000+ employees).**
>
> Why they look like a fit: more PHI, more risk, more email.
>
> Why they aren't a fit: they have dedicated IT and procurement teams. Our self-serve motion doesn't work. Their security requirements add 6+ month enterprise sales cycles. Better served by enterprise security vendors.

---

## What good ICP discipline looks like for your function

After a few months of working with this template, write a paragraph here. The paragraph should describe what good ICP discipline produces in your work. Specific qualities, not generic ones.

Example direction: "When this template is doing its job, content sounds like it was written by someone who has actually talked to a practice administrator. Campaigns target the trigger events, not the title alone. We say no to leads that look interesting but fail the firmographic check."

`[Your description of what good looks like]`

---

*This template is shared as part of [The AI Marketing Department](https://theaimarketingdepartment.substack.com), a Substack about building an AI demand gen team in public.*
