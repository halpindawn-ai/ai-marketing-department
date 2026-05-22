# AI Employee Role Spec Template

A copy-and-use template for scoping AI employees in your function. Based on the PMM framework: every employee has operators, experts, and references.

This is a demo version. Fill in the bracketed placeholders with your own answers. Copy this file, rename it for the employee you're scoping, and start writing. Most of mine took 2–3 drafts before they felt right.

The actual specs in my AI demand gen team run 1,000+ lines each. This is the bones.

---

## 1. Identity

**Employee name:** `[Function-coded title. Examples: "Paid Acquisition Manager," "Customer Marketing Manager," "Sales Enablement Manager"]`

**Function:** `[The work this employee owns end to end. One sentence.]`

**Business goal:** `[What success looks like. Not activity, outcome. "Generate qualified pipeline at efficient CAC," not "run good ads."]`

**Reports to:** `[The human manager. That's you.]`

---

## 2. Maturity level

Where this employee sits today, on a 1–4 scale:

- **Level 1: Assistant.** Some skills built. You still drive most workflows.
- **Level 2: Operator.** Several skills shipping. Some workflows chained.
- **Level 3: Expert.** Most workflows automated. You approve, don't execute.
- **Level 4: Employee.** Full workflow ownership. You manage by exception.

Current level: `[1 / 2 / 3 / 4]`

The honest answer here matters more than the aspirational one. Level 1 is fine. Level 1 means you've started.

---

## 3. Skill inventory

Every Claude skill mapped to its role within this employee.

| Skill | Role | Function | Status |
|---|---|---|---|
| `[skill-name]` | Operator | `[What it does in one line]` | BUILT |
| `[skill-name]` | Operator | `[What it does in one line]` | PARTIAL |
| `[skill-name]` | Expert | `[What it does in one line]` | BUILT |
| `[skill-name]` | Reference | `[What it provides]` | BUILT |
| `[gap-name]` | Operator | `[What's missing]` | GAP |

Three role types, from the PMM framework:

- **Operator:** human-defined, AI-executed. Recurring workflows.
- **Expert:** AI knowledge, human judgment. On-demand analysis and recommendations.
- **Reference:** passive knowledge. What operators and experts read from.

---

## 4. Operators, experts, and references

The same skills as Section 3, organized by role for a faster scan.

### Operators

`[skill-name]` → `[Outcome it produces]`

`[skill-name]` → `[Outcome it produces]`

### Experts

`[skill-name]` → `[Judgment it provides]`

### References

`[skill-name]` → `[Knowledge it stores]`

### Gaps

`[gap-name]` → `[What you'd want this to do once built]`

---

## 5. Infrastructure beyond Claude

The systems this employee depends on outside the AI layer. Could be a CRM, an ads platform, a database, a Google Sheet, anything.

- **`[System name]`:** `[What lives there and why this employee reads from or writes to it]`
- **`[System name]`:** `[What lives there]`

This section gets skipped a lot. Don't skip it. The infrastructure layer is what turns "smart prompts" into "a thing that actually runs."

---

## 6. End-to-end workflows

The recurring processes this employee runs. Each workflow chains operators (and sometimes experts) together with human checkpoints.

### Workflow 1: `[Name]`

**Trigger:** `[What kicks it off. Scheduled? On-demand? Triggered by an event?]`

**Steps:**

1. `[skill]` → `[What happens]`
2. `[skill]` → `[What happens]`
3. `[skill]` → `[What happens]`

**Human checkpoint:** `[Where you review, approve, or override]`

**Status:** `[Built / Partial / Gap]`

### Workflow 2: `[Name]`

`[Repeat the structure.]`

Most employees have 2–5 real workflows. If you can't name at least two, the employee probably isn't a distinct role yet.

---

## 7. Handoff points

Where this employee's work touches other AI employees (current or future). Every cross-employee request goes through you.

| Direction | From / To | What gets handed off |
|---|---|---|
| Receives from | `[Other employee]` → `[This employee]` | `[Content / data / signal]` |
| Sends to | `[This employee]` → `[Other employee]` | `[Content / data / signal]` |

The handoffs are the part most people skip when they design AI teams. Skip them and the team drifts. Define them and the team stays coordinated through you.

---

## 8. Gap analysis

What's missing, ordered by leverage.

### Priority 1: `[High/Medium/Low] impact, [Not started / Partial]`

**`[Gap name]`**

`[1–2 sentences on what's missing and what closing it would unlock. Be specific about the build target.]`

### Priority 2: ...

`[Repeat. Usually 4–7 priorities total per employee.]`

The first priority should be the highest-leverage gap, not the easiest. If the easiest gap also happens to be the highest-leverage one, you're lucky. If not, do the harder thing first.

---

## 9. What "Level 4" looks like

The end state. At Level 4, the employee owns the function. Editorial judgment and final approval stay with you, but execution doesn't.

### What runs without you

`[Free-form list of capabilities that will be fully automated at Level 4. Be concrete.]`

### What still requires you

`[Free-form list of decisions that stay human. Be honest. The list is usually shorter than people expect.]`

This section is the goal post. If you don't know what Level 4 looks like for an employee, you don't know where you're building toward.

---

## 10. Operating manual (three-file shape)

The operating manual for this employee. Auto-loads before any task in their scope.

I used to write this as a single system-prompt block. In practice that block grows past 1,000 lines and becomes unreadable, and editing one quarterly detail means re-reading the whole thing. The shape I use now splits it into three files that auto-load together:

```
skills/[your-prefix]-[employee-name]/
  SKILL.md              ← the router
  structural-rules.md   ← permanent guardrails
  commanders-intent.md  ← quarterly state
```

**`SKILL.md` (router).** Identity, skill inventory and routing table, routing rules ("one intent, one delegation," "never substitute," approval gates), workflow pipelines, the handoff protocol, and a standard output shape for reporting back. Does no execution work itself — it delegates to the operators, experts, and references from Section 3.

**`structural-rules.md` (permanent guardrails).** Primary optimization target, audit/diagnostic order, compliance rules, operating rules (numbered and additive so new rules never reorder old ones), deliverable structure, evaluation frameworks, decision triggers, permanent corrections. Lifespan test: if it would still be true in two quarters with a different roadmap and a different channel mix, it goes here.

**`commanders-intent.md` (quarterly state).** Current maturity level (from Section 2), current posture (which channels, programs, or paths are active vs. under evaluation vs. declined), baseline corrections, the current quarter's build roadmap (from Section 11), planned skill additions (from Section 8), and the current Level N+1 target. Always dated at the top. This is the file that goes stale fastest.

Why split it: you can change quarterly intent without touching the rules, the router stays thin, and each layer is independently legible — someone can read just the rules without parsing routing logic. You can't get those properties from one big block. It has to be three files.

Set the router to auto-load before any task in the employee's scope. The two supporting files load via a "Read first" block at the top of the router.

---

## 11. Build plan

How you're going to get this employee from where it is now to Level 4. Phased, with each phase closing one or more gaps from Section 8.

| Phase | Status | What ships |
|---|---|---|
| Phase 1 | `[Complete / In flight / Next]` | `[Description]` |
| Phase 2 | `[Status]` | `[Description]` |
| Phase 3 | `[Status]` | `[Description]` |
| Phase 4 | `[Status]` | `[Description]` |

Don't try to close every gap at once. Sequence them by leverage. The first phase should always be "wrap and document what exists" so you know your starting point.

---

## How to use this template

1. **Copy this file and rename it for the employee you're scoping.** One employee per file. If you're scoping a marketing function with five employees, you end up with five files.
2. **Fill in the brackets.** Don't worry about getting it right the first time. The template is meant to be iterated on.
3. **Write the org chart from the specs, not the other way around.** The handoffs in Section 7 are where the cross-employee structure emerges. If you draw an org chart first, you'll back-fill it with assumptions. If you write the specs first, the chart writes itself.
4. **Use Section 8 (gap analysis) as your build roadmap.** Don't try to close every gap at once. Sequence by leverage.
5. **Build the operating-manual skill from Section 10.** The three-file shape — router, permanent rules, quarterly intent — is what makes the spec actually run. It's the difference between "AI that knows the role" and "AI that has to be told the role every time."
6. **Treat sections 2, 8, and 11 as quarterly.** Maturity level, gap priorities, and the build plan rotate as the work moves. Everything else (identity, skill inventory, workflows, handoffs, Level 4) is stable. The three-file shape in Section 10 mirrors that cadence — quarterly state lives in its own file so you can update it without touching the rules.

---

## Why this format works

This template is the work-product behind every employee in **The AI Marketing Department**, my Substack about building an AI demand gen team in public. The actual specs run 1,000+ lines each. They cover the same eleven sections, plus details specific to each function.

The format borrows from PMM frameworks (employees as roles with specs, not as tools) and from product documentation conventions (gaps and phases as first-class structure). It's intentionally heavier than a one-page role description. Lighter docs end up being aspirational. This one stays honest because every section forces a concrete answer.

If you use this for your own team, I'd love to see what you're building. Reply to any issue of the newsletter and tell me what you're scoping.
