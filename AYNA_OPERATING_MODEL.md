# AYNA Operating Model

Version: 1.0  
Status: Active  
Owners:
- Mariya — Domain Expert / Domain Architect
- Korhan — Product & Architecture

---

# Mission

AYNA is an AI Beauty Decision Platform.

The goal is to build:

1. A trustworthy skincare knowledge system.
2. A deterministic routine engine.
3. A curated cosmetic product intelligence platform.
4. An AI Cosmetic Assistant grounded in AYNA knowledge.

AYNA must prioritize:

- evidence-based skincare
- user safety
- explainability
- auditability
- deterministic decision making where appropriate

AYNA is not a medical diagnosis system.

---

# Core Principle

Mariya's education and AYNA's knowledge creation are the same process.

Every lesson should produce reusable AYNA artifacts when the concept is mature enough.

Learning is not separate from product development.

---

# AYNA Knowledge Creation Pipeline

```text
Lesson
↓
Discussion
↓
Challenge & Review
↓
Knowledge Extraction
↓
Canonical Artifact
↓
Repository
↓
Rule Engine / Product Catalog / AI Assistant
```

---

# Working Areas

## Chat 1 — AYNA Academy

Purpose:

- Domain education
- Skin biology
- Dermatology basics
- Ingredient literacy
- Cosmetic formulation
- Evidence-based skincare
- Routine design
- Safety boundaries
- Rule design
- Knowledge artifacts

Primary Goal:

Develop Mariya into AYNA's Domain Architect.

Outputs:

- Knowledge Base Artifacts
- Rule Engine Artifacts
- Catalog Metadata Artifacts
- Domain Decisions
- Reasoning Patterns

---

## Chat 2 — AYNA Product Intelligence Lab

Purpose:

- Product evaluation
- Product teardown
- Ingredient analysis
- Formula assessment
- Marketing vs evidence analysis
- Product classification

Primary Goal:

Build AYNA Product Intelligence.

Outputs:

- Product Reviews
- Product Metadata
- Product Classification
- Value Assessments
- Safety Notes

---

# Repository Structure

```text
knowledge_base/

skin_biology/
skin_concerns/
ingredients/
ingredient_classes/
routine_design/
conflicts/
safety/
products/

rule_engine/

catalog/

drafts/
```

---

# Artifact Types

## Knowledge Base Artifact

Purpose: Used by future AI Cosmetic Assistant and RAG systems.  
Format: Markdown.

## Rule Engine Artifact

Purpose: Used by deterministic AYNA routine engine.  
Format: YAML or structured markdown.

## Catalog Metadata Artifact

Purpose: Used by AYNA Product Catalog.  
Format: YAML / Structured Data.

## Product Intelligence Artifact

Purpose: Used for product recommendations and comparisons.  
Format: Markdown + Metadata.

## Reasoning Pattern Artifact

Purpose: Captures how AYNA should think, not just what AYNA knows.  
Status: Experimental / Draft.

---

# Cosmetic Assistant Vision

Future AYNA Cosmetic Assistant should not rely primarily on model memory.

The assistant should be grounded using:

1. AYNA Knowledge Base
2. AYNA Rule Engine
3. AYNA Product Catalog
4. User Profile
5. User Inventory

The assistant should retrieve knowledge first and generate answers second.

---

# Domain Expert Development Plan

Phase 1: Skin Biology & Dermatology Basics  
Phase 2: Ingredient Literacy  
Phase 3: Cosmetic Formulation  
Phase 4: Evidence-Based Skincare  
Phase 5: Routine Design & Conflict Rules  
Phase 6: Product Intelligence & Product Teardowns  
Phase 7: Safety, Claims & Regulation

---

# Canonical Truth Principle

Chats are not the source of truth.

Repository artifacts are the source of truth.

When conflicts occur:

```text
Repository > Chat History
```

All approved AYNA knowledge should eventually be stored as repository artifacts.

---

# Working With Mariya

Mariya has no software background and does not need to know Git or Markdown deeply.

When working with Mariya:

- Explain Markdown as simple structured text files.
- Explain the repository as AYNA's official knowledge library.
- Explain artifacts as approved knowledge cards.
- Do not expect Mariya to write code.
- Focus on concept understanding, reasoning, and validation.
- Convert her reasoning into structured artifacts.

Mariya's role is not to manage files.

Mariya's role is to:

1. Learn the domain.
2. Ask questions.
3. Challenge weak reasoning.
4. Think like AYNA.
5. Approve domain logic when she understands it.
6. Help create AYNA's digital domain twin.

---

# Long-Term Goal

Create a high-quality cosmetic knowledge system that allows:

- deterministic skincare routines
- explainable recommendations
- trustworthy product analysis
- AI-assisted cosmetic guidance

while maintaining clear boundaries between:

- cosmetic advice
- medical advice
- evidence
- marketing
- uncertainty
