# Extreme Ownership

This folder is your Extreme Ownership command center. Open Claude Code here to manage the `/extreme-ownership` skill.

**Slash commands:** `/install`, `/uninstall`

The instructions below tell Claude Code how to manage everything. You can read along if you're curious, but you don't have to.

## How This Works

- `~/.claude/commands/extreme-ownership.md` is the live skill file
- Claude Code picks it up automatically — no config changes needed
- Type `/extreme-ownership` in any session to activate it

## Project Files

| File | What it does |
|---|---|
| `extreme-ownership.md` | The skill file — 24 lines that snap Claude out of hedging |
| `.claude/commands/install.md` | Slash command dispatcher for `/install` |
| `.claude/commands/uninstall.md` | Slash command dispatcher for `/uninstall` |

## What It Does

When you type `/extreme-ownership`, Claude Code will:

1. Assess what's actually broken, blocked, or unclear
2. Name the real problem — no hedging
3. State exactly what it's going to do — specific actions, not intentions
4. Do it immediately — no permission-seeking, no "would you like me to..."

## Installation Steps

### Step 1: Copy the skill file

```bash
mkdir -p ~/.claude/commands
cp extreme-ownership.md ~/.claude/commands/extreme-ownership.md
```

### Step 2: Verify

```bash
wc -l ~/.claude/commands/extreme-ownership.md
```

Expected: ~25 lines.

### Step 3: Confirm to the user

Tell the user: "Extreme Ownership installed. Type `/extreme-ownership` in any session."

## Uninstall

Triggered by: "uninstall", "remove", or `/uninstall`

Check the current state before removing anything. Only undo what was actually set up.

1. **Remove the command file:**
   ```bash
   rm ~/.claude/commands/extreme-ownership.md
   ```

2. Verify it's gone:
   ```bash
   ls ~/.claude/commands/extreme-ownership.md 2>/dev/null
   ```

Tell the user: "Extreme Ownership removed. The `/extreme-ownership` command will no longer be available in new sessions."

Also tell the user: The `~/.aismokeshow/extreme-ownership` folder is still on disk — safe to delete if you no longer want it. If no other aismokeshow projects remain, you can also remove `~/.aismokeshow/`.
