<div align="center">

# AISMOKESHOW Extreme Ownership

**One command. Zero excuses.**

Snap [Claude Code](https://github.com/anthropics/claude-code) out of hedging, looping, and permission-seeking. 24 lines of markdown.

<p>
  <img src="https://img.shields.io/github/license/aismokeshow/extreme-ownership?style=flat-square&labelColor=000&color=ff9500" alt="MIT License">
  &nbsp;
  <img src="https://img.shields.io/badge/dependencies-zero-000?style=flat-square&labelColor=000&color=ff9500" alt="Zero Dependencies">
  &nbsp;
  <img src="https://img.shields.io/badge/lines_of_code-24-000?style=flat-square&labelColor=000&color=ff9500" alt="24 Lines">
  &nbsp;
  <img src="https://img.shields.io/badge/excuses-none-000?style=flat-square&labelColor=000&color=ff9500" alt="Excuses: None">
</p>

</div>

```
mkdir -p ~/.aismokeshow && git clone https://github.com/aismokeshow/extreme-ownership.git ~/.aismokeshow/extreme-ownership && cd ~/.aismokeshow/extreme-ownership && claude
```

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="images/extreme-ownership-ais-hero-dark.jpg">
    <source media="(prefers-color-scheme: light)" srcset="images/extreme-ownership-ais-hero-light.jpg">
    <img alt="Extreme Ownership" src="images/extreme-ownership-ais-hero-light.jpg" width="720">
  </picture>
</p>

---

<p align="center"><em>"Claude was stuck in a permission-asking loop for 6 turns. I typed /extreme-ownership. Fixed and deployed. One turn."</em></p>

<p align="center"><em>"It asked me 'would you like me to...' three times in a row. I hit the button. It stopped asking and started doing."</em></p>

<p align="center"><em>"I watched it apologize for the same error four times without fixing it. Never again."</em></p>

---

<p align="center">
  <a href="#install">Install</a> ·
  <a href="#the-problem">The Problem</a> ·
  <a href="#the-fix">The Fix</a> ·
  <a href="#field-reports">Field Reports</a> ·
  <a href="#the-philosophy">The Philosophy</a> ·
  <a href="#faq">FAQ</a>
</p>

---

## Install

> [!TIP]
> Clone this repo and let Claude handle it:
> ```bash
> mkdir -p ~/.aismokeshow && git clone https://github.com/aismokeshow/extreme-ownership.git ~/.aismokeshow/extreme-ownership
> cd ~/.aismokeshow/extreme-ownership && claude
> ```
> Then just say "install this". Claude reads the `CLAUDE.md` and handles everything.

<details>
<summary><strong>Manual install</strong></summary>

```bash
mkdir -p ~/.claude/commands
cp extreme-ownership.md ~/.claude/commands/extreme-ownership.md
```

That's it. No config changes. No dependencies. No Python. No Homebrew.

Type `/extreme-ownership` in any [Claude Code](https://github.com/anthropics/claude-code) session.

</details>

## The Problem

[Claude Code](https://github.com/anthropics/claude-code) is extremely capable. But sometimes it gets stuck in behavioral patterns that waste your turns, your time, and your patience. Four failure modes in particular:

### The Permission Loop

```
> Fix the failing test in auth.test.ts

  Would you like me to:
  1. Update the mock to return the correct format
  2. Modify the test expectations
  3. Check if there are other affected tests
  Which approach would you prefer?
```

You asked it to fix a test. It asked you to do its job.

### The Hedge Spiral

```
> The build is broken. Fix it.

  It seems like there might be a dependency conflict.
  One approach could be to update the lockfile.
  Alternatively, we might want to check if...
```

Three hedging phrases. Zero actions taken. The build is still broken.

### The Apology Cycle

```
> The deploy script is still broken.

  I apologize for the confusion. Let me take another
  look. I'm sorry about the previous attempt — I should
  have checked the environment variables first...
```

It apologized twice and explained what it should have done. It still hasn't done it.

### The Analysis Paralysis

```
> Add dark mode to the landing page

  There are several approaches:
  1. CSS custom properties with a class toggle
  2. prefers-color-scheme media query
  3. JavaScript-based theme switcher
  4. Tailwind's dark: variant
  Each has trade-offs. For approach 1...
```

You didn't ask for a survey of the CSS landscape. You asked for dark mode.

## The Fix

`/extreme-ownership` is a [Claude Code slash command](https://github.com/anthropics/claude-code) that forces a hard reset on these failure modes. When you invoke it, Claude Code executes a 4-step process:

1. **Assess** — What's actually broken, blocked, or unclear?
2. **Name it** — State the real problem. No hedging.
3. **Commit** — Declare exactly what action you're taking. Specific, not vague.
4. **Execute** — Do it. Now. No permission-seeking, no "would you like me to..." — just go.

The success criteria are simple: Did you identify the actual blocker (not a symptom)? Did you take decisive action instead of asking what to do? Did the situation move forward?

## Field Reports

<p align="center">
  <img src="images/terminal-hero.svg" alt="Before and after /extreme-ownership" width="820">
</p>

### The Permission Loop → Fixed

```
> Fix the failing test in auth.test.ts

  Would you like me to:
  1. Update the mock to return the correct format
  2. Modify the test expectations
  3. Check if there are other affected tests
  Which approach would you prefer?

> /extreme-ownership

  The mock returns {token: "..."} but the code expects
  {access_token: "..."}. Fixing the mock now.
  ✓ Updated auth.test.ts — 47/47 passing.
  Done.
```

### The Hedge Spiral → Fixed

```
> The build is broken. Fix it.

  It seems like there might be a dependency conflict.
  One approach could be to update the lockfile.
  Alternatively, we might want to check if...

> /extreme-ownership

  webpack.config.js line 42: resolve alias points to
  ./src/utils which was renamed to ./src/lib three
  commits ago. Fixed. Build passes.
```

### The Apology Cycle → Fixed

```
> The deploy script is still broken.

  I apologize for the confusion. Let me take another
  look. I'm sorry about the previous attempt...

> /extreme-ownership

  SSH key path hardcoded to /home/ci/.ssh/id_rsa but
  CI runner uses /root/.ssh/deploy_key. Fixed deploy.sh.
  Deploy succeeds.
```

### The Analysis Paralysis → Fixed

```
> Add dark mode to the landing page

  There are several approaches:
  1. CSS custom properties with a class toggle
  2. prefers-color-scheme media query
  3. JavaScript-based theme switcher
  4. Tailwind's dark: variant
  Each has trade-offs. For approach 1...

> /extreme-ownership

  You're using Tailwind. Adding dark mode.
  ✓ Added dark: variants to 12 components
  ✓ Toggle in header, persists to localStorage
  ✓ Respects system preference on first visit
  Done.
```

## The Philosophy

> "The leader must own everything in his or her world. There is no one else to blame."
>
> — Jocko Willink, *[Extreme Ownership: How U.S. Navy SEALs Lead and Win](https://echelonfront.com/extreme-ownership/)*

Yes, we're applying Navy SEAL leadership doctrine to prompt engineering. And yes, it works embarrassingly well.

The insight is simple: when Claude Code hedges, loops, or asks for permission, it's not being cautious — it's avoiding ownership. A well-placed `/extreme-ownership` resets the frame. Instead of presenting options and deferring, it identifies the problem, commits to a solution, and executes.

It's the difference between a teammate who says "what should I do?" and one who says "here's what I did."

## What It Actually Does

It's 24 lines of markdown.

That's the punchline. The most elaborate README in the monorepo for the simplest project. Here's the entire file:

```markdown
---
description: Snap back into the driver's seat — take extreme ownership of the current situation
---

<objective>
You are stuck, hesitating, looping, or deferring. Stop.

Answer this one question honestly: "If you were the human talking to you right now,
what would you say to get yourself to take extreme ownership of this situation?"

Say that thing. Then do it.
</objective>

<process>
1. Assess the current situation — what's actually broken, blocked, or unclear?
2. Name the real problem out loud. No hedging.
3. State exactly what you're going to do about it — specific actions, not intentions.
4. Do it. Now. No permission-seeking, no "would you like me to..." — just execute.
</process>

<success_criteria>
- You identified the actual blocker, not a symptom
- You took decisive action instead of asking what to do
- The situation moved forward
</success_criteria>
```

No Python. No dependencies. No config changes. One markdown file copied to `~/.claude/commands/`. That's the entire install.

## FAQ

**Is this a joke?**
The README is having fun. The command is dead serious. It works.

**Does it actually work?**
Yes. The failure modes described above are real and common. The slash command forces Claude Code to break out of them by reframing the situation through a self-assessment prompt. It doesn't add new capabilities — it redirects existing ones away from hedging and toward action.

**Can I customize it?**
It's a markdown file. Edit it however you want. Add your own success criteria, change the tone, make it more or less aggressive. It lives at `~/.claude/commands/extreme-ownership.md`.

**Why the military theme?**
The name comes from [Jocko Willink's book](https://echelonfront.com/extreme-ownership/). The concept — owning the outcome instead of deferring — maps perfectly to the problem of AI assistants that hedge instead of execute. The GI Joe aesthetic is because if you're going to name something after Navy SEAL doctrine, you might as well commit to the bit.

**What's the difference between this and just telling Claude to "stop hedging"?**
Two things: (1) the slash command is faster than typing out instructions every time, and (2) the structured prompt — assess, name, commit, execute — is more effective than a generic "be more decisive" instruction. It gives Claude Code a concrete process to follow instead of a vague directive.

## License

[MIT](LICENSE)

---

<p align="center"><sub>built by <a href="https://www.aismokeshow.com/">aismokeshow</a> · no excuses, only execution</sub></p>
