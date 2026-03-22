# Blueprint 📐

**Engineering plan review — lock architecture, data flow, and test coverage before you code**

[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blue)](https://openclaw.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Free on ClawMart](https://img.shields.io/badge/ClawMart-Free-success)](https://www.shopclawmart.com/listings/gstack-eng-e0c6a11c)

---

## What It Does

Once Compass approves the *direction*, Blueprint nails down the *implementation*: architecture diagrams, state machines, data flows, failure modes, edge cases, and test matrices.

**What you get:**
- 📊 ASCII architecture diagrams (mandatory, not optional)
- 🔄 State machine flows for complex logic
- ⚠️ Failure modes registry (every error named, rescued, tested)
- 🧪 Test coverage matrix
- 📋 TODOS.md updates for implementation tracking

---

## Why It Matters

Teams often have the right product direction but weak technical execution:

| Without Blueprint | With Blueprint |
|-------------------|----------------|
| N+1 queries discovered in production | Caught in review |
| Silent failures in error paths | Every failure mode named |
| Missing tests for edge cases | Test matrix generated |
| Stale documentation | Diagrams forced to match code |
| Coupled architecture | DRY violations flagged |

Blueprint ensures "engineered enough" — not under-engineered, not over-engineered.

---

## Installation

### Option 1: ClawMart (Recommended)
```
Visit: https://www.shopclawmart.com/listings/gstack-eng-e0c6a11c
```

### Option 2: Manual
```bash
git clone https://github.com/NovaCaliforniaLabs/blueprint-skill.git
cp -r blueprint-skill ~/.openclaw/workspace/skills/blueprint
```

---

## Usage

```
/blueprint
# Skill asks: "What existing code solves sub-problems?"
# You describe: "Building a rate limiter"
# Skill asks: "Touching >8 files or >2 new classes?"
# You select: B) Big Change
# Skill produces architecture diagram, test matrix, flags N+1 queries
# Output: Implementation spec ready for coding
```

---

## Scope Challenge (Step 0)

Before reviewing implementation, Blueprint checks:

| Question | Catches |
|----------|---------|
| Can existing code solve this? | Reinventing wheels |
| Is this the minimum change? | Over-engineering |
| Is complexity justified? | Premature abstraction |

---

## Review Sections

1. **Architecture** — diagrams, state machines, data flow
2. **Code Quality** — DRY violations, coupling, naming
3. **Test Diagram** — coverage matrix, edge cases
4. **Performance** — latency budgets, N+1 detection

---

## Example Output

```
📐 Blueprint: Rate Limiter
━━━━━━━━━━━━━━━━━━━━━━━━━

## Architecture:
┌─────────────┐    ┌──────────────┐    ┌─────────────┐
│  Request    │───▶│  RateLimiter │───▶│  Handler    │
│  (IP/Key)   │    │  (Redis)      │    │  (passed)   │
└─────────────┘    └──────────────┘    └─────────────┘
                         │
                         ▼
                  ┌──────────────┐
                  │  Counter TTL │
                  │  (1min window)│
                  └──────────────┘

## Failure Modes:
| Error | Rescue | Test |
|-------|--------|------|
| Redis down | Fallback to memory | ✓ |
| Counter overflow | Reset + log | ✓ |
| Invalid key | 400 response | ✓ |

## Issues Found:
⚠️ N+1 detected: Counter reads in loop
⚠️ Missing: TTL cleanup for expired keys

## TODOS.md:
- [ ] Add Redis connection pooling
- [ ] Implement key TTL cleanup
- [ ] Add integration tests for Redis down
```

---

## From Garry Tan's gstack

Part of the gstack workflow: Compass (CEO) → **Blueprint (Eng)** → Ship → Mirror (retro).

---

## License

MIT — free for personal and commercial use.

---

**[Get it free on ClawMart →](https://www.shopclawmart.com/listings/gstack-eng-e0c6a11c)**
