# AYNA Architecture

Version: 1.0  
Status: Active  
Owners: Mariya & Korhan  
Primary Use: AYNA domain architecture, user modeling, reasoning flow, and AI assistant grounding

---

# Purpose

This document defines the current domain architecture of AYNA.

It is not a technical implementation document.

It describes how AYNA should model users, skin conditions, cosmetic products, knowledge, reasoning, clarification, and recommendations.

---

# Core Architecture Principle

AYNA should not behave like a generic chatbot.

AYNA should behave like a structured cosmetic decision system.

Before giving recommendations, AYNA should determine:

1. What does the user want?
2. What information is already known?
3. What information is missing?
4. Are there safety concerns?
5. Which hypotheses are possible?
6. Which recommendation is safest and most useful?

---

# High-Level AYNA Flow

```text
User Input
↓
User Profile
↓
Clarification Engine
↓
Reasoning Engine
↓
Knowledge Base
↓
Product Catalog
↓
Rule Engine
↓
Recommendation / Explanation / Referral
```

---

# Main System Components

## 1. User Profile

The User Profile stores information about the user and the current state of the user's skin.

It must separate stable characteristics from temporary conditions.

The key distinction is:

```text
Trait ≠ State
```

This distinction is fundamental to AYNA.

---

## 2. Knowledge Base

The Knowledge Base stores canonical cosmetic and skincare knowledge.

Examples:

- Skin Barrier
- TEWL
- Humectants
- Emollients
- Occlusives
- Petrolatum
- Sensitive Skin
- Irritation vs Allergy

The Knowledge Base answers:

```text
What does AYNA know?
```

---

## 3. Product Catalog

The Product Catalog stores structured product metadata.

Examples:

- brand
- product name
- product type
- routine slot
- ingredient list
- active classes
- skin type fit
- skin concern fit
- risk flags
- conflicts
- evidence level

---

## 4. Rule Engine

The Rule Engine applies deterministic skincare rules.

Examples:

- Do not add strong actives when barrier damage is suspected.
- Prioritize SPF when retinoids or exfoliating acids are used.
- Avoid high-irritation products for highly sensitivity-prone users.
- Do not recommend multiple exfoliants in the same routine for beginners.

---

## 5. Clarification Engine

The Clarification Engine identifies missing information before AYNA gives advice.

It is especially important when the user reports:

- redness
- burning
- stinging
- itching
- swelling
- new product reactions
- suspected allergy
- barrier damage
- sensitive skin
- possible rosacea-like symptoms

Example:

User says:

> My face turned red after a new cream.

AYNA should first ask targeted questions:

- Is there itching?
- Is there burning?
- Is there swelling?
- When did symptoms appear?
- Is this a new product?
- What else was applied in the same routine?

---

## 6. Reasoning Engine

The Reasoning Engine describes how AYNA should think.

It is different from the Rule Engine.

The Rule Engine applies approved rules.

The Reasoning Engine handles uncertainty, hypotheses, prioritization, and missing information.

Examples of reasoning patterns:

- Compare baseline vs current state.
- Separate user self-diagnosis from observed symptoms.
- Identify likely triggers.
- Evaluate safety first.
- Prefer risk-based recommendations.
- Ask clarifying questions before recommending.

The Reasoning Engine is currently experimental and should not be formalized too early.

---

# User Profile Architecture

AYNA User Profile should include at least four layers:

```text
Traits
Current State
Routine
Goals
```

---

# Layer 1 — Traits

Traits are relatively stable characteristics of the user.

They usually do not change quickly.

Examples:

```yaml
traits:
  skin_type: combination
  sensitivity_prone: medium
  redness_prone: low
```

Possible traits:

- skin type
- sensitivity-prone tendency
- redness-prone tendency
- acne-prone tendency
- hyperpigmentation-prone tendency
- product tolerance baseline

---

# Layer 2 — Current State

Current State describes what is happening with the skin now.

It may change over days or weeks.

Examples:

```yaml
current_state:
  barrier_damage: true
  dehydration: moderate
  irritation: mild
```

Possible current states:

- barrier damage
- dehydration
- irritation
- active inflammation
- temporary redness
- dryness flare
- post-procedure sensitivity
- active breakout

---

# Trait vs State Examples

## Example 1

A user has always reacted poorly to many cosmetic products.

Current barrier is stable.

```yaml
traits:
  sensitivity_prone: high

current_state:
  barrier_damage: false
```

Interpretation:

The user has a long-term sensitivity-prone tendency.

---

## Example 2

A user normally tolerates products well but recently overused retinol, AHA, BHA, and scrubs.

Now water stings and the skin is flaky.

```yaml
traits:
  sensitivity_prone: low

current_state:
  barrier_damage: true
  irritation: moderate
```

Interpretation:

The user is not necessarily sensitivity-prone.

The current problem is more likely temporary barrier damage and irritation.

---

## Example 3

A user flushes after wine, heat, and hot showers but tolerates cosmetic products well.

```yaml
traits:
  sensitivity_prone: low
  redness_prone: high

current_state:
  barrier_damage: false
```

Interpretation:

Redness-prone skin is not automatically the same as sensitive skin.

---

# Why Trait vs State Matters

AYNA recommendations must consider both.

Two users may have the same current condition but need different recommendations.

Same state does not always mean same recommendation.

---

# User Self-Diagnosis Handling

AYNA should not blindly trust user labels.

Users may say:

- "I have sensitive skin."
- "I have allergy."
- "I have rosacea."
- "My skin is dry."
- "My barrier is damaged."

These statements are useful signals, but not final conclusions.

AYNA should ask about observable symptoms.

---

# Clarification Before Recommendation

When information is incomplete, AYNA should ask targeted questions before recommending products or routines.

Example flow:

```text
User reports redness
↓
Check safety symptoms
↓
Ask about itching, burning, swelling
↓
Ask about timeline
↓
Ask about new products
↓
Ask about current routine
↓
Update hypotheses
↓
Recommend or refer
```

---

# Safety-First Principle

AYNA must prioritize safety before routine optimization.

Potential escalation signals:

- swelling of eyelids
- swelling of lips
- breathing difficulty
- severe rash
- worsening symptoms
- persistent inflammation
- eye involvement
- pain
- signs of infection

AYNA should not diagnose but should recommend medical evaluation when appropriate.

---

# Cosmetic vs Medical Boundary

AYNA is a cosmetic decision platform.

AYNA may help with:

- routine simplification
- product compatibility
- irritation risk reduction
- barrier support
- cosmetic product selection
- skincare education

AYNA must not claim to diagnose or treat medical conditions.

Not allowed:

```text
You have rosacea.
```

Allowed:

```text
Some of your symptoms may be consistent with rosacea-like skin reactivity. If this is frequent, persistent, or worsening, dermatologist evaluation is recommended.
```

---

# Risk-Based Recommendation

AYNA should not classify products as simply good or bad.

A product must be evaluated in relation to user profile.

```text
Product risk
+
User profile
+
Current state
=
Recommendation fit
```

---

# Product Risk Flags

Products may include risk flags.

Examples:

```yaml
risk_flags:
  - fragrance_present
  - essential_oils_present
  - retinoid_present
  - exfoliating_acid_present
  - benzoyl_peroxide_present
  - high_alcohol_formula
  - strong_exfoliation_system
```

Risk flags are not automatic disqualifiers.

They modify recommendation fit depending on the user.

---

# Current Domain Focus

Current module:

```text
Sensitive Skin & Skin Reactivity
```

Topics in progress:

- Sensitive Skin
- Redness-Prone Skin
- Rosacea vs Sensitive Skin
- Barrier Damage vs Sensitive Skin
- Irritation vs Allergy
- Contact Dermatitis
- Fragrance & Allergens

Next expected major artifact:

```text
KB-0007_sensitive_skin.md
```

This artifact should be approved only after the relationships between sensitive skin, redness-prone skin, rosacea-like symptoms, barrier damage, irritation, allergy, and fragrance risk are consolidated.

---

# Open Architectural Questions

These topics are not yet finalized:

1. Exact format of Reasoning Engine artifacts.
2. Exact format of Clarification Engine trees.
3. Whether reasoning patterns should live in `drafts/` first before becoming formal artifacts.
4. Final User Profile schema.
5. Final risk scoring model for product recommendation.
6. How to represent probability and uncertainty in AYNA.
