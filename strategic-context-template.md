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


---

## 2. Goals

The specific outcomes this function is trying to hit. Be concrete. "Grow pipeline" is not a goal. "Generate $3M in attributed pipeline this quarter, with a CAC below $X" is a goal.

**This quarter:**
- `[Goal 1]`: `[target, deadline]`
- `[Goal 2]`: `[target, deadline]`

**This year:**
- `[Goal 1]`: `[target]`
- `[Goal 2]`: `[target]`

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

---

## 6. Decision frameworks

How you choose between options. Encoded so the AI can apply the same logic you would, not whatever logic seems reasonable in the moment.

**Framework 1:** `[Name of decision]`

`[The rubric or rule you apply]`

**Framework 2:** `[Name of decision]`

`[The rubric or rule you apply]`

---

## 7. Current priorities

What you're working on right now. Updated quarterly or whenever the focus shifts.

**Top three this quarter:**
1. `[Priority 1]`: `[why now]`
2. `[Priority 2]`: `[why now]`
3. `[Priority 3]`: `[why now]`

**What we're not doing right now (and why):**
- `[Thing we're not doing]`: `[why we're holding off]`

---

## 8. Out of scope

The work that explicitly does not belong to this function. Helps the AI not drift into adjacent territory and helps it route requests correctly.

`[Work type]`: `[why it's out of scope]` `[who owns it instead]`

---

## What good looks like for your function

Once you have a few months of working with this template, come back and write a paragraph here. The paragraph should describe what "good strategic discipline" looks like in your function. Not abstract; the actual texture of decisions made well.

`[Your description of what good looks like]`

---

*This template is shared as part of [The AI Marketing Department](https://theaimarketingdepartment.substack.com), a Substack about building an AI demand gen team in public.*
