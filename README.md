<div align="center">

# AISMOKESHOW Extreme Ownership

**One command. Zero excuses.**

Snap [Claude Code](https://github.com/anthropics/claude-code) out of hedging, looping, and permission-seeking — and keep it out for the rest of the session.

<p>
  <img src="https://img.shields.io/github/license/aismokeshow/extreme-ownership?style=flat-square&labelColor=000&color=ff9500" alt="MIT License">
  &nbsp;
  <img src="https://img.shields.io/badge/dependencies-zero-000?style=flat-square&labelColor=000&color=ff9500" alt="Zero Dependencies">
  &nbsp;
  <img src="https://img.shields.io/badge/anti--patterns-5_diagnosed-000?style=flat-square&labelColor=000&color=ff9500" alt="5 Anti-Patterns">
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
  <a href="#v2--whats-new">v2</a> ·
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

[Claude Code](https://github.com/anthropics/claude-code) is extremely capable. But sometimes it gets stuck in behavioral patterns that waste your turns, your time, and your patience. Five failure modes in particular:

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

### The Relay

```
> Why is the API returning 500 errors?

  I looked at the logs and found several errors related
  to the database connection pool. The pool is exhausting
  under load. Here are some things we could look at:
  - Connection pool size
  - Query optimization
  - Connection timeouts
  What would you like me to investigate first?
```

It found the problem. Then handed it back to you instead of fixing it.

## The Fix

`/extreme-ownership` is a [Claude Code slash command](https://github.com/anthropics/claude-code) that forces a hard reset on these failure modes. When you invoke it, Claude Code executes a structured intervention:

1. **Diagnose** — Name which anti-pattern is active (The Relay, The Menu, The Hedge, The Loop, or The Permission Slip)
2. **Assess** — What's actually broken, blocked, or unclear?
3. **Name it** — State the real problem. No hedging.
4. **Commit** — Declare exactly what action you're taking. Specific, not vague.
5. **Execute** — Do it. Now. No permission-seeking, no "would you like me to..." — just go.

After executing, it outputs **Rules of Engagement** that persist in context for the rest of the session, preventing relapse into the same patterns.

## v2 — What's New

v1 was a one-shot jolt. It fixed the current moment, but the effect faded. v2 upgrades the intervention into a **persistent ownership loop** with three new capabilities:

### Pattern Diagnosis

Before acting, v2 identifies WHICH specific anti-pattern is active:

| Anti-Pattern | What It Looks Like |
|---|---|
| **The Relay** | Gathered info, presented it, asked what to do |
| **The Menu** | Listed options instead of picking one |
| **The Hedge** | Tentative language — "might", "could", "perhaps" |
| **The Loop** | Repeated the same failed approach |
| **The Permission Slip** | Asked approval for something obvious |

Naming the pattern out loud is what makes the intervention surgical instead of generic. It's the difference between "stop hedging" and "you're running The Menu — pick option 2 and execute it."

### Session-Persistent Rules

After taking action, Claude outputs explicit Rules of Engagement:

```
RULES OF ENGAGEMENT (active for remainder of session):
1. Act, then report. Never report without acting.
2. One option, executed. Not three options, presented.
3. If you need information, get it yourself. Don't ask the user for information you can find.
4. If exploration is needed, spawn a subagent. Keep this thread for decisions and actions.
5. Every response must contain something you DID, not just something you FOUND.
```

These rules persist in Claude's conversation context and influence all subsequent turns — not through any special mechanism, just through how context windows naturally work. The rules stay in context until [compaction](https://docs.anthropic.com/en/docs/claude-code/overview), which typically happens deep into long sessions.

### Subagent Delegation

When the stuck state involves needing to explore code, errors, or logs, v2 instructs Claude to spawn an exploration subagent instead of exploring in the main thread. This prevents the cycle that causes relapse: exploration fills context → Claude loses focus → starts relaying findings instead of acting on them.

This is NOT a multi-agent framework. It's a single tactical rule: delegate exploration, keep the main thread for decisions and actions.

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

### The Relay → Ownership Loop (v2)

```
> Why is the API returning 500 errors?

  I checked the logs and found database connection pool
  exhaustion under load. Here are some options:
  - Increase pool size
  - Optimize slow queries
  - Add connection timeouts
  What would you like me to investigate?

> /extreme-ownership

  PATTERN: The Relay — I found the problem, then handed
  it back instead of fixing it.

  The connection pool max is 5, traffic is 200 req/s.
  Spawning subagent to find the pool config location...
  Found: src/db/config.ts line 12.
  ✓ Increased pool max to 25
  ✓ Added connection timeout of 5000ms
  ✓ Added idle timeout of 10000ms
  ✓ Restarted dev server — 0 connection errors

  RULES OF ENGAGEMENT (active for remainder of session):
  1. Act, then report. Never report without acting.
  2. One option, executed. Not three options, presented.
  3. If you need information, get it yourself.
  4. If exploration is needed, spawn a subagent.
  5. Every response must contain something you DID.
```

## The Philosophy

> "The leader must own everything in his or her world. There is no one else to blame."
>
> — Jocko Willink, *[Extreme Ownership: How U.S. Navy SEALs Lead and Win](https://echelonfront.com/extreme-ownership/)*

Yes, we're applying Navy SEAL leadership doctrine to prompt engineering. And yes, it works embarrassingly well.

The insight is simple: when Claude Code hedges, loops, or asks for permission, it's not being cautious — it's avoiding ownership. A well-placed `/extreme-ownership` resets the frame. Instead of presenting options and deferring, it identifies the problem, commits to a solution, and executes.

It's the difference between a teammate who says "what should I do?" and one who says "here's what I did."

v2 takes this further. Instead of resetting the frame for one turn, it installs operating rules that keep the ownership frame active for the entire session. The diagnosis step makes the intervention specific — not "be more decisive" but "you're running The Hedge, here's the real problem, now fix it." The rules persist in context and influence every subsequent response.

## What It Actually Does

It's ~55 lines of markdown. Still one file. Still zero dependencies.

The v2 upgrade adds three sections to the original 4-step process:

1. **Pattern Recognition** — diagnose which of five named anti-patterns is active
2. **Rules of Engagement** — output session-persistent rules that prevent relapse
3. **Subagent Delegation** — keep the main thread clean by delegating exploration

The core process (assess → name → commit → execute) is unchanged. It gets more effective because the diagnosis is more specific.

## FAQ

**Is this a joke?**
The README is having fun. The command is dead serious. It works.

**Does it actually work?**
Yes. The failure modes described above are real and common ([GitHub issue #22557](https://github.com/anthropics/claude-code/issues/22557)). The slash command forces Claude Code to break out of them by reframing the situation through a structured self-assessment. It doesn't add new capabilities — it redirects existing ones away from hedging and toward action.

**What's new in v2?**
Three things: (1) pattern diagnosis — Claude names WHICH anti-pattern it's running before fixing it, (2) session-persistent rules — explicit operating rules that stay in context and influence all subsequent turns, and (3) subagent delegation — exploration goes to a subagent so the main thread stays clean for action. Still one file, still zero dependencies.

**How do the rules persist?**
No magic. The Rules of Engagement are output as text in the conversation. They stay in Claude's context window and influence subsequent responses — the same way any instruction in the conversation does. They persist until [context compaction](https://docs.anthropic.com/en/docs/claude-code/overview), which typically happens deep into long sessions. If you notice the effect fading, just invoke `/extreme-ownership` again.

**Can I customize it?**
It's a markdown file. Edit it however you want. Add your own anti-patterns, change the rules, adjust the tone. It lives at `~/.claude/commands/extreme-ownership.md`.

**Why the military theme?**
The name comes from [Jocko Willink's book](https://echelonfront.com/extreme-ownership/). The concept — owning the outcome instead of deferring — maps perfectly to the problem of AI assistants that hedge instead of execute. The GI Joe aesthetic is because if you're going to name something after Navy SEAL doctrine, you might as well commit to the bit.

**What's the difference between this and just telling Claude to "stop hedging"?**
Three things: (1) the slash command is faster than typing out instructions every time, (2) the structured intervention — diagnose the anti-pattern, then assess → name → commit → execute — is more effective than a generic "be more decisive" instruction, and (3) the session-persistent rules prevent relapse, which a one-off instruction can't do.

## License

[MIT](LICENSE)

---

<p align="center"><sub>built by <a href="https://www.aismokeshow.com/">aismokeshow</a> · no excuses, only execution</sub></p>
