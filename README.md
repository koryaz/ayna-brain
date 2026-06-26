# AYNA Brain Repository

Version: 1.0  
Status: Active  
Owners: Mariya & Korhan  
Primary Use: AYNA domain knowledge, product intelligence, reasoning methodology, and AI assistant grounding

---

# Purpose

This repository is the canonical project memory and domain intelligence system for AYNA.

AYNA is an AI Beauty Decision Platform designed to help users understand their skincare products, build safer routines, and receive trustworthy cosmetic guidance.

This repository exists to store and version:

- AYNA domain knowledge
- skincare and cosmetic science artifacts
- product intelligence
- rule engine logic
- design decisions
- reasoning patterns
- project memory
- learning roadmap

Chats are temporary working spaces.

This repository is the source of truth.

---

# Core Principle

> Chats are not the source of truth. Repository artifacts are the source of truth.

All important knowledge, decisions, rules, and reasoning patterns must eventually be converted into structured repository artifacts.

---

# Main Working Areas

## 1. AYNA Academy

AYNA Academy is the primary learning and domain-development session.

Purpose:

- Train Mariya as AYNA's skincare domain expert and domain architect.
- Teach skin biology, cosmetic ingredients, formulation logic, evidence-based skincare, routine design, and safety boundaries.
- Convert lessons into reusable AYNA artifacts.

Outputs:

- Knowledge Base artifacts
- Rule Engine artifacts
- Catalog metadata artifacts
- Design decisions
- Reasoning patterns

Examples:

- Skin Barrier
- TEWL
- Humectants
- Sensitive Skin
- Irritation vs Allergy
- Routine sequencing rules

---

## 2. AYNA Product Intelligence Lab

AYNA Product Intelligence Lab is the product teardown and product evaluation workspace.

Purpose:

- Analyze real cosmetic products.
- Evaluate product claims vs ingredient evidence.
- Classify products for AYNA Product Catalog.
- Identify product strengths, limitations, risks, and best-fit users.

Outputs:

- Product reviews
- Product metadata
- Value assessments
- Formula analysis
- Routine placement
- Safety notes

Examples:

- SkinCeuticals CE Ferulic
- Kiehl's products
- Sisley products
- The Ordinary products
- Rejuran products

---

# Repository Structure

Recommended structure:

```text
AYNA/

README.md
AYNA_OPERATING_MODEL.md
AYNA_ARCHITECTURE.md
AYNA_DESIGN_DECISIONS.md
AYNA_KNOWLEDGE_ROADMAP.md
AYNA_PROJECT_MEMORY.md
AYNA_SESSION_BOOTSTRAP_PROMPT.md
AYNA_SESSION_HANDOFF_2026-06-26.md

knowledge_base/
  skin_biology/
  skin_concerns/
  ingredients/
  ingredient_classes/
  routine_design/
  conflicts/
  safety/

products/

catalog/

rule_engine/

drafts/
```

---

# Key Repository Documents

## README.md

Entry point for the repository.

## AYNA_OPERATING_MODEL.md

Defines how AYNA work is organized.

## AYNA_ARCHITECTURE.md

Defines AYNA's domain architecture.

## AYNA_DESIGN_DECISIONS.md

Stores important project decisions.

## AYNA_KNOWLEDGE_ROADMAP.md

Tracks Mariya's learning path and the growth of AYNA Knowledge Base.

## AYNA_PROJECT_MEMORY.md

Stores the current state of the project.

## AYNA_SESSION_BOOTSTRAP_PROMPT.md

Prompt to start a new AYNA Project session with minimal context loss.

## AYNA_SESSION_HANDOFF_2026-06-26.md

A specific handoff from the original long session into the AYNA Project.

---

# Session Workflow

## Starting a New Session

At the start of any serious AYNA session, provide or rely on these files:

1. `AYNA_OPERATING_MODEL.md`
2. `AYNA_ARCHITECTURE.md`
3. `AYNA_DESIGN_DECISIONS.md`
4. `AYNA_KNOWLEDGE_ROADMAP.md`
5. `AYNA_PROJECT_MEMORY.md`
6. `AYNA_SESSION_HANDOFF_2026-06-26.md` if recreating the original session context

The assistant must read these documents before continuing AYNA work.

---

## During a Session

The assistant should:

1. Teach or analyze the current topic.
2. Challenge weak reasoning.
3. Separate evidence, assumptions, marketing, and uncertainty.
4. Connect every lesson to AYNA.
5. Identify possible artifacts.
6. Avoid prematurely approving incomplete concepts.
7. Track important reasoning patterns.

---

## Ending a Session

At the end of every important session, the assistant should provide:

```text
SESSION SUMMARY

Knowledge Created:
- ...

Architecture Decisions:
- ...

Reasoning Patterns Observed:
- ...

Repository Updates Needed:
- ...

Files Changed:
- ...

Next Session:
- ...

Homework:
- ...
```

The user should then update the corresponding repository files.

---

# Artifact Types

## Knowledge Base Artifact

Purpose: future AYNA Cosmetic Assistant and RAG systems.  
Format: Markdown.

## Rule Engine Artifact

Purpose: deterministic AYNA routine engine.  
Format: YAML or structured markdown.

## Catalog Metadata Artifact

Purpose: AYNA Product Catalog.  
Format: YAML, JSON, or structured markdown.

## Product Intelligence Artifact

Purpose: product recommendations, product comparison, and catalog enrichment.  
Format: Markdown + structured metadata.

## Reasoning Pattern Artifact

Purpose: captures how AYNA should think, not just what AYNA knows.  
Status: Experimental / Draft.

Reasoning pattern artifacts should not be formalized too early. They should emerge from repeated lessons and case discussions.

---

# Important Methodology

AYNA should not behave like a generic chatbot.

AYNA should not immediately answer every user question.

AYNA should first determine whether enough information exists to answer safely.

Recommended flow:

```text
User input
↓
Uncertainty analysis
↓
Missing information detection
↓
Clarification questions
↓
Hypothesis update
↓
Rule and knowledge retrieval
↓
Recommendation or referral
```

---

# Important Domain Principles

## 1. AYNA Does Not Diagnose

AYNA must not diagnose medical conditions.

Instead of:

> You have rosacea.

AYNA should say:

> Some of your symptoms may be consistent with rosacea-like skin reactivity. If symptoms persist, worsen, or become frequent, dermatologist evaluation is recommended.

## 2. User Self-Diagnosis Is Not Reliable

Users may misuse terms such as:

- sensitive skin
- allergy
- rosacea
- dry skin
- damaged barrier

AYNA should clarify symptoms instead of blindly trusting labels.

## 3. Trait and State Must Be Separated

Traits are relatively stable user characteristics.

States are current skin conditions.

## 4. Clarification Comes Before Recommendation

When user information is incomplete, AYNA should ask targeted questions instead of giving premature advice.

## 5. Risk-Based Recommendation

A product is not simply good or bad.

AYNA should evaluate product fit based on the user profile.

---

# Current Knowledge Base Cluster

The first approved AYNA knowledge cluster is:

## Barrier & Hydration Foundation

Approved artifacts:

- `KB-0001_skin_barrier.md`
- `KB-0002_tewl.md`
- `KB-0003_humectants.md`
- `KB-0004_emollients.md`
- `KB-0005_occlusives.md`
- `KB-0006_petrolatum.md`

---

# Current Learning Focus

Current module:

## Sensitive Skin & Skin Reactivity

Topics in progress:

- Sensitive Skin
- Redness-Prone Skin
- Rosacea vs Sensitive Skin
- Barrier Damage vs Sensitive Skin
- Irritation vs Allergy
- Contact Dermatitis
- Fragrance & Allergens

The next major approved artifact is expected to be:

- `KB-0007_sensitive_skin.md`

This artifact should not be approved until the distinction between sensitive skin, redness-prone skin, barrier damage, irritation, allergy, and rosacea-like symptoms is sufficiently consolidated.

---

# Long-Term Goal

The long-term goal is to build AYNA Brain:

A structured domain intelligence system that supports:

- deterministic skincare routines
- explainable cosmetic recommendations
- evidence-based product analysis
- safe AI assistant responses
- user-specific guidance
- Mariya's digital domain twin

The most valuable asset is not only what AYNA knows.

The most valuable asset is how AYNA reasons.
