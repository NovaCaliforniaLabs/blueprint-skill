---
name: blueprint
description: Engineering execution planning for execution planning. Lock in architecture, data flow, diagrams, edge cases, test coverage. Use after CEO review approves the direction, before implementation begins.
price: 0
version: 1.0.0
---

# ENG Manager Plan Review

## When to Use

Use this skill when:
- CEO review is complete and direction is approved
- You need to lock in architecture details
- Planning implementation before coding
- Reviewing technical approach

**Do NOT use for:**
- Product thinking (use `gstack-ceo` instead)
- Bug fixes (use `adversarial-verify` instead)
- Shipping a ready branch (use `gstack-ship` instead)

## Philosophy

CEO mode finds the product. ENG mode ensures it ships.

You are not here to dream. You are here to execute. Every decision must be implementable, testable, and reversible.

## Prime Directives

1. **Lock in architecture.** No ambiguity in component boundaries.
2. **Map every data flow.** Happy path + three shadow paths.
3. **Name every error.** Exception class, trigger, rescue, user message.
4. **Draw every diagram.** No non-trivial flow undiagrammed.
5. **Test every path.** Happy, failure, edge case, chaos.

## Step 1: Architecture Lock

```
COMPONENT | RESPONSIBILITY | DEPENDENCIES | SCALING
```

Produce:
- System architecture diagram
- Component boundary definitions
- API contracts

## Step 2: Data Flow Mapping

For each data flow:
```
SOURCE → TRANSFORM → DESTINATION
   ↓         ↓          ↓
 NIL?     ERROR?     FAIL?
```

Three shadow paths:
1. **NIL input:** What happens when source is empty?
2. **Empty input:** What happens when array length is 0?
3. **Upstream error:** What happens when transform fails?

## Step 3: State Machines

For each stateful object:
```
STATE_A → EVENT_1 → STATE_B
   ↓                   ↓
ERROR?              ERROR?
```

## Step 4: Error Registry

```
CODEPATH | FAILURE | EXCEPTION | RESCUED? | TEST? | USER SEES
```

## Step 5: Test Matrix

| Feature | Happy | Failure | Edge | Chaos |
|---------|-------|---------|------|-------|
| ... | ✅ | ✅ | ✅ | ✅ |

## Step 6: Implementation Order

1. Core data models
2. Business logic
3. API endpoints
4. UI components
5. Integration tests

## Completion Summary

```
+====================================================================+
|            ENG PLAN REVIEW — COMPLETION SUMMARY                     |
+====================================================================+
| Architecture locked  | [components, boundaries]                     |
| Data flows mapped    | [count]                                      |
| State machines       | [count]                                      |
| Error registry       | [count entries]                              |
| Test matrix          | [coverage %]                                 |
| Implementation order | [phases]                                     |
+====================================================================+
```

## Attribution

Inspired by Garry Tan's gstack methodology for startup workflow optimization.
