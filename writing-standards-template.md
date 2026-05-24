# Writing Standards Template

A markdown file that codifies how your brand sounds in writing. Load it as a Claude Code reference skill, paste it into a prompt as instructions, or use it as a self-check before publishing.

The point of this template is to give every AI skill in your stack one source of truth for voice, tone, and editorial conventions. When you update the file, every skill that loads it picks up the change automatically.

Fill in the bracketed placeholders with your own answers. The examples below each section are illustrative. Replace them with your own when you have your own.

---

## How to use it

**As a Claude Code skill.** Save this file as `writing-standards/SKILL.md` in your skills folder. Reference it from any content-producing skill so the standards auto-load before drafting.

**As a prompt instruction.** Paste the rules below into any prompt when you ask Claude to draft something for your brand. Add: *"Apply these writing standards to the draft below."*

**As a self-check.** Read the Quick-Check Reference at the bottom before publishing anything.

---

## 1. Voice

The way your brand sounds. List 3 to 5 adjectives that describe the voice, plus 3 to 5 things the voice is not. Specificity matters more than poetry.

**We sound:**
- `[adjective]`: `[brief explanation]`
- `[adjective]`: `[brief explanation]`
- `[adjective]`: `[brief explanation]`

**We don't sound:**
- `[anti-adjective]`: `[why we avoid this]`
- `[anti-adjective]`: `[why we avoid this]`

*Illustrative example:*

> We sound:
> - Direct: lead with the point, not setup
> - Conversational: short sentences, contractions, occasional fragments
> - Opinionated: take a stance, don't hedge
>
> We don't sound:
> - Corporate: no "leveraging synergies"
> - Breathlessly enthusiastic: no "we're so excited" openers
> - Tourism-coded: no "rich heritage" or "vibrant ecosystem"

---

## 2. Editorial principles

The structural rules that apply to every piece. Not specific words, but how the work is built.

`[Principle 1]`: `[what it means in practice]`

`[Principle 2]`: `[what it means in practice]`

`[Principle 3]`: `[what it means in practice]`

*Illustrative example:*

> **Front-load every paragraph.** Lead with the point, then explain. Most readers scan; reward the scanners.
>
> **Source every claim.** Link, name a person, or cite a specific number. "Studies show" without a citation is a deletion candidate.
>
> **Active voice, concrete subjects.** "We reduced churn by 12%" beats "A reduction in churn was achieved."
>
> **Short sentences mixed with long.** Rhythm matters. Three medium sentences in a row reads as monotone.

---

## 3. Tone calibration

Different content types deserve different tones. Be specific about what changes between them.

| Content type | Tone | Special rules |
|---|---|---|
| `[type 1]` | `[tone descriptor]` | `[rules unique to this type]` |
| `[type 2]` | `[tone descriptor]` | `[rules unique to this type]` |
| `[type 3]` | `[tone descriptor]` | `[rules unique to this type]` |

*Illustrative example:*

| Content type | Tone | Special rules |
|---|---|---|
| Blog posts | Authoritative + conversational | Front-load the point; source every claim; subheaders break up scrollable text |
| Social posts | Casual + direct | Hook in the first sentence; one idea per post |
| Emails | Warm + transactional | Honor the inbox; one ask per email |
| Press releases | Newsworthy + specific | Lead with the most contradictory finding; no neutral data summaries |

---

## 4. Terminology

The word choices that define your voice. Two lists: preferred terms and avoided terms.

**Preferred terms:**
- `[term]` instead of `[alternative]`
- `[term]` instead of `[alternative]`

**Avoided terms:**
- `[term]`: `[why we avoid it]`
- `[term]`: `[why we avoid it]`

*Illustrative example:*

> Preferred:
> - "Healthcare compliance" instead of "regulatory adherence" (plainer)
> - "Research library" instead of "corpus" (corpus reads as jargon)
>
> Avoided:
> - "Leverage" as a verb: use "use" or "draw on"
> - "Robust" / "seamless" / "comprehensive": AI-coded marketing language
> - "Solutions" as a noun for the product: name the product instead

---

## 5. Capitalization and formatting

The punctuation, spacing, and structural rules that catch most editors.

`[Rule 1]`: `[specification]`

`[Rule 2]`: `[specification]`

`[Rule 3]`: `[specification]`

*Illustrative example:*

> - Oxford commas always
> - One space after a period
> - Em dashes used sparingly; commas or periods preferred
> - Lists use parallel structure across items

---

## 6. Common pitfalls to avoid

Specific tells your brand hates. This is where you encode taste.

`[Pitfall 1]`: `[example, why bad]`

`[Pitfall 2]`: `[example, why bad]`

`[Pitfall 3]`: `[example, why bad]`

*Illustrative example:*

> - **LinkedIn-influencer formulas.** "Most people get X wrong." "I stopped doing X and started doing Y." Numbered list hooks. These are recognized patterns; readers tune them out.
> - **Tourism-ad tone.** "World-class," "cutting-edge," "vibrant ecosystem" do not appear.
> - **Vague attribution.** "Studies show" or "experts agree" without a name or link.
> - **Negative parallelism.** "It's not X, it's Y" patterns. State what something is, not what it isn't.
> - **Fabricated specifics.** No invented customer quotes, reactions, or "what people are saying."

---

## 7. Side-by-side examples

Two or three rewrites of "off-brand" content into "on-brand" content. This is where the abstract rules become concrete. Update these as your voice evolves.

**Off-brand:**

> `[Example of writing that misses your standards]`

**On-brand:**

> `[Same content rewritten to match]`

*Illustrative example:*

> **Off-brand:** "We're thrilled to announce our cutting-edge solution that empowers healthcare organizations to seamlessly navigate the complexities of HIPAA compliance."
>
> **On-brand:** "Our new product helps healthcare organizations stay HIPAA compliant without slowing down their email."

---

## Quick-Check Reference

Before publishing, scan for:

1. Any phrase from your "avoided terms" list
2. Em dash density: more than one per paragraph?
3. AI vocabulary: delve, foster, leverage, harness, navigate (metaphorical), pivotal, crucial?
4. Hedge-y language: "could," "might," "perhaps" without good reason?
5. Tourism tone: robust, seamless, comprehensive, world-class, cutting-edge?
6. Negative parallelism: "It's not X, it's Y" or "Not just X, but Y" patterns?
7. Vague attribution: "studies show," "experts agree" without sources?
8. LinkedIn-influencer hooks: "Most people get X wrong," "I stopped X and started Y"?
9. First-sentence load: does the opener give the reader a reason to keep reading?
10. Three-part lists: are they doing real work, or filling space?

---

## What good looks like for your brand

Once you have a few months of writing under your belt with this template, come back and write a two-paragraph summary here. The two paragraphs should describe what makes your writing recognizably yours. Specific qualities, not generic adjectives.

This section is the destination. The rules above are how you get there.

`[Your description of what good looks like for your brand]`

---

*This template is shared as part of [The AI Marketing Department](https://theaimarketingdepartment.substack.com), a Substack about building an AI demand gen team in public.*
