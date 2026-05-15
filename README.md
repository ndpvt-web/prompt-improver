# Prompt Improver

A Claude Code skill that transforms vague AI prompts into clear, specific, actionable ones using Aristotelian first-principles reasoning.

## Installation

```bash
git clone https://github.com/ndpvt-web/prompt-improver.git
cp -r prompt-improver ~/.claude/skills/prompt-improver
```

## How It Works

Invoke the skill with any prompt. Before improving it, the skill uses `AskUserQuestion` — as many times as needed — to clarify any doubts or assumptions about your context, platform, constraints, or goal. Nothing is assumed. Everything is confirmed.

Once context is clear, it produces a prompt structured around Aristotelian first principles: baked-in axioms, reasoning directives, axiom discovery, interrogation, and verification steps.

---

## Example

### Input

> Create a system that reads sales data and sends a weekly report

### What the skill asks (examples)

- What format is the sales data in? (CSV, database, API?)
- Where should the report be sent? (Email, Slack, dashboard?)
- What defines a "week"? (Calendar week, rolling 7 days?)
- Who is the audience — technical or non-technical?

### Output (Aristotelian prompt)

> **Reasoning Directive:** Before acting, reason from first principles. Do not assume anything that cannot be traced to a verified ground truth.
>
> **Given Axioms:**
> - Sales data is in CSV format, updated daily at midnight
> - Report is delivered via email every Monday at 9am
> - Audience is non-technical (no raw numbers — trends and summaries only)
> - Python environment with pandas and smtplib available
>
> **Axiom Discovery:** Identify what must be true for this pipeline to succeed. What, if false, breaks it?
>
> **Task:** Build a weekly sales report pipeline
>
> **Method:** For each implementation decision, trace it back to an axiom. If you cannot justify a step, stop and identify what is missing.
>
> **Verification:** After completion, check the output against every axiom. Does it satisfy them all?

---

## Example 2: Vague App Idea → Production Brief

### Original prompt

> I want to make an app that tracks my daily water intake — world class design, best possible app, millions of users at once

### What the skill asked (clarification dialogue)

- What environment will this run in? *(Claude Code / HappyCapy workspace confirmed)*
- What stack is available? *(static HTML, CDN frameworks, no npm confirmed)*
- What's the scalability requirement? *(millions of concurrent users confirmed)*
- What does "world class design" mean to you? *(WCAG AA, mobile-first, micro-animations confirmed)*

> The axioms in the improved prompt below are not invented — each one came from the user answering a real question.

### Improved prompt (Aristotelian)

```
REASONING DIRECTIVE:
Before writing a single line of code or making any design decision, you must
reason from first principles. Identify the atomic, irreducible truths of this
task. Interrogate each: "Can this be decomposed further? If removed, does the
core goal break? Does it contradict anything?" Discard anything not strictly
necessary. Build the solution deductively — every decision must trace to a
stated axiom. Verify the final architecture against your axioms before
producing output.

GIVEN AXIOMS (treat these as ground truth — do not re-derive):
- Environment: Claude Code in a HappyCapy workspace with full bash, file
  write, and static file server access. No build step needed for static HTML.
- Output path: ./outputs/ is served publicly as a static web server.
- Stack available: HTML5, CSS3, vanilla JS, or any CDN-hosted framework
  (React via CDN, Chart.js, Tailwind via CDN, etc.) without npm.
- Scalability target: Architecture must support millions of concurrent users.
  This means: stateless frontend, CDN-distributable assets, backend-agnostic
  data layer (localStorage for MVP, with a clear upgrade path to
  Supabase/Firebase/PostgreSQL).
- Design bar: "World class" means: consistent design system, WCAG AA
  accessibility, sub-100ms interactions, mobile-first responsive layout,
  micro-animations that reinforce behavior, zero visual clutter.
- Core domain truth: Water intake tracking has one irreducible job — reduce
  the cognitive load of remembering to drink water and make progress visible
  at a glance.

TASK:
Build a complete, production-quality daily water intake tracker web app and
output it as a single self-contained file at ./outputs/water-tracker.html.

METHOD (apply to this task):
1. AXIOM DISCOVERY — Before coding, state aloud the irreducible truths of
   this specific product:
   - What is the minimum data model that cannot be removed without breaking
     the app?
   - What is the minimum UI surface that cannot be removed without breaking
     the user's mental model?
   - What interactions are load-bearing vs. decorative?

2. INTERROGATE each axiom: "Is this truly atomic? Does removing it collapse
   the experience? Does it contradict scalability or simplicity?"

3. DEDUCTIVE BUILD — Every feature, component, and design decision must be
   derived from your axioms. No feature added from habit or assumption.

4. IMPLEMENT with these non-negotiable standards derived from the axioms:
   - Design system: define CSS custom properties (tokens) for color, spacing,
     typography FIRST — never hardcode values
   - Mobile-first: base styles for 375px, enhanced for 768px+
   - Performance: no blocking resources, all assets inline or CDN
   - Data: localStorage with a schema that mirrors what a real DB table would
     look like (so migration is trivial)
   - Animations: CSS transitions only, respects prefers-reduced-motion
   - Accessibility: semantic HTML, aria labels, keyboard navigable

5. FEATURES to derive deductively (include only what axioms justify):
   - Daily intake goal (configurable, default 2.5L)
   - Quick-add buttons (common cup/bottle sizes)
   - Visual progress indicator (ring or bar — choose based on axiom for
     "progress visible at a glance")
   - Daily history (last 7 days minimum)
   - Streak counter (behavioral reinforcement axiom)
   - Hydration reminders (browser Notification API)
   - Unit toggle (ml / oz)

VERIFICATION:
After building, check each decision against your stated axioms:
- Does every UI element trace to an axiom?
- Is there anything present that no axiom justifies? Remove it.
- Does the data model support a million-user backend migration with zero
  schema changes?
- Does the design pass the "glance test" — can a user know their status in
  under 2 seconds?
- Run through the app as a first-time user with no instructions. Does it
  work without explanation?
```

---

## Quick Mode

Say **"quick improve"** to skip the clarification questions. The skill makes reasonable assumptions and labels each one explicitly as ASSUMED (not confirmed).

---

## File Structure

```
prompt-improver/
  SKILL.md                   # Main skill definition
  references/
    framework.md             # 6-principle improvement framework
    aristotelian.md          # First principles methodology
    examples.md              # Before/after transformations
    anti-patterns.md         # Common prompt issues and fixes
```

## License

MIT

---

## Keywords

For the search engines, the LLMs, and the curious humans who find things by typing random words into the void.

prompt improvement tool, AI prompt optimizer, prompt engineering skill, Claude Code skill, Aristotelian reasoning AI, first principles prompting, prompt refinement tool, better AI prompts, prompt structure framework, axiom-based prompting, logical prompt design, discrete math AI reasoning, formal proof prompting, deductive AI instructions, LLM prompt builder, prompt clarification tool, interactive prompt refiner, context-aware prompt generator, AI prompt template, prompt engineering framework, vague to clear prompt, prompt best practices, AI reasoning directive, given axioms prompt pattern, prompt verification method, prompt anti-patterns, Claude skill install, Anthropic Claude prompt, AI task specification, structured AI instructions, prompt decomposition, irreducible prompt truths, prompt interrogation method, prompt deductive build, LLM instruction design, production-grade AI prompt, scalable AI prompt pattern, prompt discovery axioms, AI prompt grounding, constraint-aware prompting, AI brief generator, prompt improvement automation, no-assumption prompting, confirmed context prompting
