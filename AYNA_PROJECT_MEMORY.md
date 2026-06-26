# AYNA Project Memory

Version: 1.0  
Status: Active  
Owners: Mariya & Korhan  
Primary Use: Current project state, session continuity, short-term memory, and next-step tracking  
Last Updated: 2026-06-26

---

# Purpose

This document stores the current working memory of the AYNA project.

It is designed to preserve continuity between AI-assisted sessions.

Chats are temporary.

This file should be updated at the end of important AYNA sessions so that future sessions can continue without losing context.

---

# Current Project Mode

Current mode:

```text
AYNA Academy
```

Primary focus:

```text
Mariya domain education + AYNA knowledge creation
```

Current module:

```text
Sensitive Skin & Skin Reactivity
```

Current objective:

To help Mariya understand and model the differences between:

- sensitive skin
- redness-prone skin
- barrier damage
- irritation
- allergic reaction
- contact dermatitis
- rosacea-like symptoms
- fragrance and allergen risk

This module will eventually produce `KB-0007_sensitive_skin.md`, but the artifact is not ready for Approved status yet.

---

# Current Repository Status

Korhan created the repository and added:

```text
AYNA_OPERATING_MODEL.md
knowledge_base/skin_biology/KB-0001_skin_barrier.md
```

The following project memory files have now been created for repository continuity:

```text
README.md
AYNA_ARCHITECTURE.md
AYNA_DESIGN_DECISIONS.md
AYNA_KNOWLEDGE_ROADMAP.md
AYNA_PROJECT_MEMORY.md
AYNA_SESSION_BOOTSTRAP_PROMPT.md
AYNA_SESSION_HANDOFF_2026-06-26.md
```

Approved Barrier & Hydration Foundation files should also be added:

```text
knowledge_base/skin_biology/KB-0002_tewl.md
knowledge_base/ingredient_classes/KB-0003_humectants.md
knowledge_base/ingredient_classes/KB-0004_emollients.md
knowledge_base/ingredient_classes/KB-0005_occlusives.md
knowledge_base/ingredients/KB-0006_petrolatum.md
```

---

# Source of Truth Principle

```text
Chats are not the source of truth.
Repository artifacts are the source of truth.
```

All important knowledge, architecture, decisions, and reasoning patterns should eventually be converted into repository artifacts.

---

# Current Approved Knowledge Cluster

## Barrier & Hydration Foundation

Approved KB artifacts:

```text
KB-0001_skin_barrier.md
KB-0002_tewl.md
KB-0003_humectants.md
KB-0004_emollients.md
KB-0005_occlusives.md
KB-0006_petrolatum.md
```

---

# Current Module: Sensitive Skin & Skin Reactivity

Status:

```text
In Progress
```

Topics already discussed:

```text
Sensitive Skin
Redness-Prone Skin
Rosacea vs Sensitive Skin
Barrier Damage vs Sensitive Skin
Irritation vs Allergy
Contact Dermatitis
Fragrance & Allergens
Clarification before Recommendation
Trait vs State
```

Topics still requiring consolidation:

```text
Rosacea-like symptoms vs redness-prone skin
Sensitive skin vs barrier damage
Sensitive skin vs allergy
Contact dermatitis
Fragrance allergen risk
Safety escalation rules
```

Expected next major artifact:

```text
KB-0007_sensitive_skin.md
```

Current status:

```text
Not ready for Approved status.
Can be drafted after consolidation.
```

---

# Latest Important Discoveries

## 1. Trait ≠ State

Traits are relatively stable characteristics of the user.

Examples:

```text
skin_type
sensitivity_prone
redness_prone
product_tolerance_baseline
```

States are current conditions of the skin.

Examples:

```text
barrier_damage
dehydration
irritation
temporary_redness
active_flare
```

Important implication:

```text
Sensitive skin is closer to a Trait.
Barrier damage is a State.
```

---

## 2. Redness-Prone Skin ≠ Sensitive Skin

A user may flush after wine, heat, hot showers, emotions, or stress while still tolerating cosmetic products well.

This user may be:

```yaml
sensitivity_prone: low
redness_prone: high
```

AYNA should not automatically classify redness-prone users as sensitive.

---

## 3. Barrier Damage ≠ Sensitive Skin

A user who normally tolerates products well may temporarily develop burning, stinging, tightness, and flaking after overusing actives.

This should be modeled as:

```yaml
sensitivity_prone: low
current_state:
  barrier_damage: true
```

AYNA should not permanently classify the user as sensitive unless baseline history supports it.

---

## 4. User Self-Diagnosis Is Not Final

Users may say:

```text
I have sensitive skin.
I have allergy.
I have rosacea.
My barrier is damaged.
My skin is dry.
```

These statements are useful signals but not final conclusions.

AYNA should ask about observable symptoms, timeline, triggers, and product context.

---

## 5. Clarification Comes Before Recommendation

When user input involves redness, burning, itching, swelling, or new product reaction, AYNA should not immediately recommend products.

AYNA should first ask high-value clarification questions.

---

## 6. Product Fit Must Be Risk-Based

Products are not simply good or bad.

A product must be evaluated relative to:

```text
Product risk
+
User traits
+
Current skin state
+
Routine context
```

---

## 7. Reasoning Patterns Are Emerging

Mariya is beginning to reason through cases by asking:

- What changed?
- What was the baseline?
- Which symptoms are present?
- Which symptoms are absent?
- What is the timeline?
- Is this a safety issue?
- What information is missing?
- Which hypothesis is more likely?
- Should AYNA ask more questions before recommending?

This reasoning should eventually be captured as Reasoning Engine artifacts, but the format is not ready yet.

---

## 8. Latest Lesson: Redness vs Sensitivity vs Rosacea-like Symptoms

Recent lesson clarified:

- Redness-prone skin is not automatically sensitive skin.
- Vascular reactivity can exist with good product tolerance.
- Visible vessels near the nose plus flushing after heat/alcohol raises `rosacea_suspected: possible`, not diagnosis.
- AYNA should use medical-boundary language, not diagnostic statements.
- If cosmetics are tolerated well, tolerated retinol does not need automatic discontinuation.
- Cosmetic zone recommendation: gentle cleanser, SPF, barrier-support moisturizer, avoid harsh overuse, monitor triggers.

Example profile from case:

```yaml
traits:
  sensitivity_prone: low
  redness_prone: medium/high
  vascular_reactivity: medium/high

current_state:
  barrier_damage: no/low
  irritation: low

medical_boundary:
  rosacea_suspected: possible
```

---

# Current Open Questions

## Architecture

```text
What should the final Reasoning Engine artifact format be?
What should the Clarification Engine tree format be?
Should reasoning patterns live in drafts first?
How should uncertainty and probability be represented?
How detailed should User Profile schema be in v1?
```

## Sensitive Skin Module

```text
How should AYNA define sensitivity_prone?
How should AYNA distinguish sensitive skin from redness-prone skin?
How should AYNA distinguish sensitive skin from barrier damage?
How should AYNA handle rosacea-like symptoms safely?
How should AYNA classify fragrance risk?
When should AYNA refer to dermatologist?
```

---

# Current Stable Design Decisions

```text
Repository artifacts are canonical source of truth.
Mariya's education and AYNA knowledge creation are the same process.
AYNA Academy and Product Intelligence Lab are separate working areas.
Trait and State must be modeled separately.
User self-diagnosis should not be accepted as final.
Clarification comes before recommendation when uncertainty or safety risk is present.
AYNA must not diagnose medical conditions.
Product recommendations must be risk-based and user-specific.
Redness-prone skin and sensitive skin must be distinguished.
Barrier damage and sensitive skin must be distinguished.
Reasoning patterns should not be formalized too early.
Sensitive Skin artifact should not be approved prematurely.
```

---

# Recommended Next Session

Continue AYNA Academy.

Recommended next session focus:

```text
Sensitive Skin & Skin Reactivity consolidation
```

Suggested next lesson order:

```text
1. Rosacea-like symptoms vs redness-prone skin vs sensitive skin
2. Barrier damage vs sensitive skin consolidation
3. Irritation vs allergic reaction consolidation
4. Contact dermatitis
5. Fragrance and allergen risk
6. Draft KB-0007_sensitive_skin.md
```

Do not approve `KB-0007_sensitive_skin.md` until the module is consolidated.
