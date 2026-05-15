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
