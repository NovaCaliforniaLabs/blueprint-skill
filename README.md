# blueprint

Engineering manager-mode plan review for locking in architecture, data flow, and test coverage before implementation.

## What It Does

Once CEO review approves the direction, this skill nails down implementation details: architecture diagrams, state machines, data flows, failure modes, edge cases, and test matrices. It produces mandatory ASCII diagrams, flags DRY violations, and ensures every failure mode has a named exception, rescue path, and test.

## Problem It Solves

Teams often have the right product direction but weak technical execution. This skill catches N+1 queries, missing tests, stale diagrams, coupling issues, and silent failure modes before coding begins. It ensures "engineered enough" — not under-engineered, not over-engineered.

## How to Use

1. **Run after CEO review** — direction is approved, ready for implementation details
2. **Complete Step 0** — scope challenge (existing code leverage, minimum changes, complexity check)
3. **Select mode:**
   - **A) Scope Reduction:** Plan is overbuilt, propose minimal version
   - **B) Big Change:** Work through section by section (>8 files or >2 new classes)
   - **C) Small Change:** Compressed review, one issue per section
4. **Review 4 sections** — architecture, code quality, test diagram, performance
5. **Get outputs** — failure modes registry, TODOS.md updates, diagrams, completion summary

**Example:**
```
/blueprint
# Skill asks: "What existing code solves sub-problems? Touching >8 files?"
# You select: "B) Big Change"
# Skill produces architecture diagram, test matrix, flags 3 N+1 queries
# Output: Implementation spec ready for coding
```

## Requirements

- OpenClaw installed
- Project codebase accessible
- CEO review completed (compass run first)


## One-Click Install

### Option 1: GitHub Release (Recommended)
```bash
curl -L https://github.com/NovaCaliforniaLabs/blueprint-skill/releases/latest/download/blueprint-skill.zip -o blueprint.zip
unzip blueprint.zip -d ~/.openclaw/workspace/skills/
rm blueprint.zip
```

### Option 2: ClawMart Download
After purchase on shopclawmart.com, download the package and extract to ~/.openclaw/workspace/skills/

## Quality Checklist
- ✅ SKILL.md complete with usage docs
- ✅ All scripts functional (bin/*.sh)
- ✅ Templates included (templates/)
- ✅ Examples provided (examples/)
- ✅ Attribution verified
- ✅ Tested on macOS Apple Silicon


## Pricing

$19 standalone, or included in DevFlo PRO bundle ($49 one-time).

---

*By Nova California Labs*
