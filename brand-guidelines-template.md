# Brand Guidelines Template

A markdown file that codifies your brand's visual and verbal identity in one place. Load it as a Claude Code reference skill so every content-producing skill in your stack defaults to your brand instead of generic SaaS. Update the file, and every downstream skill picks up the change.

Brand guidelines are inherently company-specific, so this template leans on structure plus prompts. Fill in your specifics. The illustrative examples are intentionally generic; the real value comes from your honest answers.

---

## How to use it

**As a Claude Code skill.** Save this file as `brand-guidelines/SKILL.md` in your skills folder. Have it auto-load before any visual asset creation, design decision, or external content draft.

**As a prompt instruction.** Paste below the request when you ask Claude to draft anything that represents your brand visually or verbally. Add: *"Apply these brand guidelines."*

**As a reference.** Use it as the source of truth when a vendor, contractor, or new team member asks "what does on-brand look like for you?"

---

## 1. Brand identity

The foundation. Who you are and what you stand for. Everything else is downstream of this.

**Brand name:** `[Your brand name]`

**Mission:** `[What your brand exists to do, in one sentence]`

**Positioning:** `[Who you serve, what problem you solve, why you're different]`

**Brand values:** `[3 to 5 values that guide decisions]`

*Illustrative example:*

> **Mission:** Make healthcare email compliance simple enough that the smallest practice can ship it.
>
> **Positioning:** The HIPAA compliant email security platform for healthcare organizations that want enterprise-grade compliance without enterprise complexity.
>
> **Brand values:** Plainspoken. Practical. Customer-led. Quietly thorough.

---

## 2. Voice

How your brand sounds in writing. List the qualities you aim for and the qualities you avoid.

**Voice descriptors (we sound):**
- `[adjective]`: `[brief explanation]`
- `[adjective]`: `[brief explanation]`
- `[adjective]`: `[brief explanation]`

**Anti-voice (we don't sound):**
- `[anti-adjective]`: `[why we avoid this]`
- `[anti-adjective]`: `[why we avoid this]`

If you have a separate writing standards file, voice can stay short here and reference there for depth.

*Illustrative example:*

> We sound:
> - Plainspoken: short sentences, real words, no jargon
> - Confident without bragging: state facts, let the reader decide
> - Customer-respectful: assume the reader is smart and busy
>
> We don't sound:
> - Corporate: no "leveraging synergies," no "transformative solutions"
> - Performatively casual: no fake informality, no exclamation overload
> - Salesy: no "act now" pressure language

---

## 3. Visual identity

The brand's visual rules. Be specific. Hex codes, font names, sizes, weights. The more concrete this section is, the less drift you get downstream.

**Primary colors:**
- `[Color name]`: `[hex code]` `[where used]`
- `[Color name]`: `[hex code]` `[where used]`

**Secondary colors:**
- `[Color name]`: `[hex code]` `[where used]`

**Typography:**
- Headlines: `[font family]`, weights `[X, Y]`
- Body: `[font family]`, weights `[X, Y]`
- UI: `[font family]`, weights `[X, Y]`

**Logo:**
- Primary lockup: `[description, file location]`
- Secondary lockup: `[description, file location]`
- Minimum size: `[pixels or inches]`
- Clear space: `[how much empty space around the logo]`

*Illustrative example:*

> Primary colors:
> - Brand navy: #0A2540 (headers, primary backgrounds)
> - Action gold: #C5A572 (CTAs, accents)
> - Off-white: #F8F7F4 (page backgrounds, light surfaces)
>
> Typography:
> - Headlines: DM Serif Display, weight 400
> - Body: DM Sans, weights 400 and 500
> - UI: DM Sans, weight 500
>
> Logo:
> - Primary: full wordmark with icon, in navy or off-white
> - Minimum size: 80px wide for digital, 0.75 inch for print
> - Clear space: at least the height of the icon on all sides

---

## 4. Imagery rules

What kind of images your brand uses and what it doesn't. Many brands skip this section and end up with inconsistent imagery. Don't skip it.

**Imagery we use:**
- `[Type]`: `[when, why]`

**Imagery we don't use:**
- `[Type]`: `[why we avoid this]`

*Illustrative example:*

> We use:
> - Real customer photos: when we have permission, in case studies
> - Branded illustrations: in landing pages and decks, all in our color palette
> - Abstract gradient backgrounds: for blog feature images, no people
>
> We don't use:
> - Stock photos of business people shaking hands or pointing at screens
> - Photography we don't own the rights to
> - Illustrations from generic libraries that get used everywhere

---

## 5. Design patterns

The recurring visual structures that hold the brand together. Cards, buttons, hierarchies, spacing. These are what make assets feel like they came from the same place.

**`[Pattern name]`:** `[when it's used, what it looks like]`

**`[Pattern name]`:** `[when it's used, what it looks like]`

*Illustrative example:*

> **Stat callout cards:** for highlighting research findings. Off-white background, navy headline (DM Serif), gold accent number. Used in reports, blog posts, and data sheets.
>
> **CTA buttons:** gold background, navy text, rounded corners. Always sentence case. Never "Click here." Always action-coded ("Read the report").
>
> **Section spacing:** 4rem between sections on web, 2rem in dense documents. Generous but not airy.

---

## 6. What we don't do

Anti-patterns. The specific visual or verbal moves that immediately read as off-brand. This is where you encode taste.

`[Anti-pattern 1]`: `[why bad]`

`[Anti-pattern 2]`: `[why bad]`

*Illustrative example:*

> - **Stock business photography.** It reads as generic. We use real customers, real illustrations, or no people at all.
> - **All-caps headlines for emphasis.** Reserved for tiny labels (eyebrow text). Headlines are sentence case in our brand's display font.
> - **Emoji in body copy.** Casual context only (Slack, internal). Never in marketing assets.
> - **Gradient text effects.** Reads as 2018 startup. Solid colors only.
> - **More than two fonts in one asset.** Display font plus body font; that's it.

---

## 7. Reference examples

Links to live assets that exemplify on-brand work. Update this section over time. The best brand guidelines have at least 5 reference examples; great ones have 10+.

- `[Asset type]`: `[link or file location]`
- `[Asset type]`: `[link or file location]`

*Illustrative example:*

> - Landing page (good): paubox.com/some-page
> - Report cover (good): link to PDF
> - Blog feature image (good): link to PNG
> - Webinar deck slide (good): link to slide
> - Social graphic (good): link to PNG

---

## What good looks like for your brand

After a few months of working with this template, write a short summary here of what makes your brand visually and verbally recognizable. Not generic adjectives. The actual texture.

`[Your description of what good looks like]`

---

*This template is shared as part of [The AI Marketing Department](https://theaimarketingdepartment.substack.com), a Substack about building an AI demand gen team in public.*
