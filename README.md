# Prompt Improver

A Claude Code skill that transforms vague AI prompts into clear, specific, actionable ones.

## Installation

```bash
git clone https://github.com/ndpvt-web/prompt-improver.git
cp -r prompt-improver ~/.claude/skills/prompt-improver
```

## Modes

### Standard Mode

Invoke the skill and it walks you through clarification questions, then produces an improved prompt. Good for prompts that just need clearer wording.

### Aristotelian Mode (Recommended)

Say **"Aristotelian"**, **"first principles"**, or **"proof-based"** when you invoke the skill.

Instead of just cleaning up your prompt, it produces a prompt that tells the AI to **reason from ground truths upward** — define its terms, build deductively, trace every decision to a stated axiom.

Use this by default. It does everything Standard mode does, plus it changes how the downstream AI reasons. The difference shows up most on complex tasks where getting the foundation wrong cascades into failure.

---

## Examples

### Standard: Vague to Specific

**Before:**
> help me write some code

**After:**
> Write a Python function that validates email addresses.
> - Accept a string input, return boolean
> - Check for valid format (user@domain.tld)
> - Handle edge cases: empty string, missing @, multiple dots
> - Include docstring with examples
> - No external dependencies

### Aristotelian: From Two Words to a Real Brief

**Before:**
> build a world-class website

**After:**
> **Reasoning Directive:** Before acting, define "world-class website" from first principles. Do not pattern-match to averages.
>
> **Given Axioms:**
> - You have access to HTML, CSS, JS, and a Linux environment
> - The goal is a live, production-grade site
>
> **Method:**
> 1. Define "world-class": decompose into speed, visual hierarchy, accessibility, conversion patterns, trust signals
> 2. Interrogate each: can it be measured? does it contradict anything else?
> 3. Build from those definitions, tracing every decision to a specific axiom
>
> **Verification:** Check the result against each axiom. Does it satisfy them all?

### Quick Mode

Say **"quick improve"** to skip questions. The skill makes reasonable assumptions and states them explicitly.

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
