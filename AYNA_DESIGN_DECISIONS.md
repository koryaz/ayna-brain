# AYNA Design Decisions

Version: 1.0  
Status: Active  
Owners: Mariya & Korhan  
Primary Use: Project decision history, architecture continuity, and long-term AI collaboration memory

---

# Purpose

This document records important design decisions made during the development of AYNA.

AYNA is not only a skincare app. It is a structured cosmetic decision system that combines:

- domain knowledge
- product intelligence
- deterministic rules
- AI assistance
- user-specific reasoning
- safety boundaries

This file exists to prevent project drift.

When a major decision is made, it should be recorded here with context, reasoning, and consequences.

---

# Decision Format

```text
Decision ID:
Title:
Status:
Date:
Context:
Decision:
Reasoning:
Consequences:
Related Files:
```

Statuses:

- Proposed
- Active
- Superseded
- Deprecated

---

# Decision-0001

## Title

Repository artifacts are the canonical source of truth.

## Status

Active

## Date

2026-06

## Context

AYNA work is being developed through long AI-assisted sessions. Chats are useful for learning, discussion, brainstorming, and artifact creation. However, long chat sessions can lose context over time, and future sessions may not have access to previous discussion details.

## Decision

The repository is the canonical source of truth for AYNA. Chats are temporary working spaces. Approved knowledge, architecture, reasoning, product evaluations, and design decisions must eventually be converted into repository artifacts.

## Reasoning

Relying on chat memory is unsafe for long-term product development. Repository files can be versioned, reviewed, updated, reused, and supplied to new AI sessions.

## Consequences

All important AYNA knowledge should eventually live in repository files. New sessions should begin by reading the current project memory files.

---

# Decision-0002

## Title

Mariya's education and AYNA knowledge creation are the same process.

## Status

Active

## Date

2026-06

## Context

Mariya is learning skincare domain knowledge to become AYNA's domain expert and domain architect. The project goal evolved: each lesson should also produce reusable AYNA knowledge.

## Decision

Mariya's learning process should generate AYNA artifacts.

## Reasoning

This creates leverage. Mariya becomes more knowledgeable while AYNA's long-term knowledge system grows at the same time.

## Consequences

Lessons should not end only with understanding. Approved concepts should be added to the repository.

---

# Decision-0003

## Title

AYNA Academy and AYNA Product Intelligence Lab are separate working areas.

## Status

Active

## Date

2026-06

## Decision

AYNA work should use two primary chat/work areas:

1. AYNA Academy
2. AYNA Product Intelligence Lab

## Reasoning

AYNA Academy is for learning, domain modeling, reasoning, and knowledge artifact creation. AYNA Product Intelligence Lab is for evaluating real cosmetic products, formulas, claims, value, and catalog metadata.

---

# Decision-0004

## Title

Trait and State must be modeled separately.

## Status

Active

## Date

2026-06

## Context

Users often describe different situations using the same language. One user may have long-term sensitivity-prone skin. Another may have temporary barrier damage from excessive actives.

## Decision

AYNA User Profile must separate Traits and Current States.

## Reasoning

Sensitive skin is not the same as barrier damage. Redness-prone skin is not the same as sensitive skin. Temporary irritation is not the same as long-term sensitivity.

## Consequences

AYNA User Profile should include separate sections:

```yaml
traits:
  skin_type:
  sensitivity_prone:
  redness_prone:
  acne_prone:
  hyperpigmentation_prone:
  product_tolerance_baseline:

current_state:
  barrier_damage:
  dehydration:
  irritation:
  active_inflammation:
  temporary_redness:
```

---

# Decision-0005

## Title

User self-diagnosis should not be accepted as final.

## Status

Active

## Date

2026-06

## Decision

AYNA should treat user self-diagnosis as input, not as truth. AYNA should clarify symptoms, timeline, triggers, and product context before making recommendations.

## Reasoning

A user saying "sensitive skin" may actually have true sensitivity-prone skin, barrier damage, irritation, allergic contact dermatitis, redness-prone skin, or rosacea-like symptoms.

---

# Decision-0006

## Title

Clarification comes before recommendation when uncertainty or safety risk is present.

## Status

Active

## Date

2026-06

## Decision

AYNA should ask targeted clarification questions before giving advice when the case involves redness, burning, stinging, itching, swelling, new product reactions, possible allergy, possible barrier damage, or possible rosacea-like symptoms.

## Reasoning

Different mechanisms require different responses. Without clarification, AYNA may make unsafe or low-quality recommendations.

---

# Decision-0007

## Title

AYNA must not diagnose medical conditions.

## Status

Active

## Date

2026-06

## Decision

AYNA must not diagnose or claim to treat medical conditions. AYNA may identify possible warning signs and recommend dermatologist evaluation when appropriate.

## Example

Not allowed:

```text
You have rosacea.
```

Allowed:

```text
Some of your symptoms may be consistent with rosacea-like skin reactivity. If this is frequent, persistent, or worsening, dermatologist evaluation is recommended.
```

---

# Decision-0008

## Title

Product recommendations must be risk-based and user-specific.

## Status

Active

## Date

2026-06

## Decision

AYNA should avoid binary product judgments such as "good" or "bad." Instead, AYNA should evaluate product fit using:

```text
Product risk
+
User traits
+
Current skin state
+
Routine context
=
Recommendation fit
```

---

# Decision-0009

## Title

Redness-prone skin and sensitive skin must be distinguished.

## Status

Active

## Date

2026-06

## Decision

AYNA should model redness-prone tendency separately from sensitivity-prone tendency.

## Reasoning

Sensitive skin is primarily related to increased reactivity and poor product tolerance. Redness-prone skin may involve vascular reactivity, flushing, or visible superficial vessels.

---

# Decision-0010

## Title

Barrier damage and sensitive skin must be distinguished.

## Status

Active

## Date

2026-06

## Decision

AYNA should model barrier damage as a current state, not as the same thing as sensitive skin.

---

# Decision-0011

## Title

Reasoning patterns should not be formalized too early.

## Status

Active

## Date

2026-06

## Decision

Reasoning Engine artifacts should initially remain experimental. They should be observed and drafted before becoming formal repository structures.

---

# Decision-0012

## Title

Sensitive Skin artifact should not be approved prematurely.

## Status

Active

## Date

2026-06

## Decision

`KB-0007_sensitive_skin.md` should not be approved until the Sensitive Skin & Skin Reactivity module is consolidated.

## Reasoning

Sensitive Skin overlaps with barrier damage, irritation, allergy, contact dermatitis, redness-prone skin, rosacea-like symptoms, and fragrance/allergen risk.

---

# Current Active Decisions Summary

1. Repository artifacts are the canonical source of truth.
2. Mariya's education and AYNA knowledge creation are the same process.
3. AYNA Academy and AYNA Product Intelligence Lab are separate working areas.
4. Trait and State must be modeled separately.
5. User self-diagnosis should not be accepted as final.
6. Clarification comes before recommendation when uncertainty or safety risk is present.
7. AYNA must not diagnose medical conditions.
8. Product recommendations must be risk-based and user-specific.
9. Redness-prone skin and sensitive skin must be distinguished.
10. Barrier damage and sensitive skin must be distinguished.
11. Reasoning patterns should not be formalized too early.
12. Sensitive Skin artifact should not be approved prematurely.
