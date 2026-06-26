# AYNA Session Handoff — 2026-06-26

Version: 1.0  
Status: Active  
Purpose: Recreate the original long AYNA Academy session context inside the new ChatGPT Project named “Ayna”.

---

# Context

This handoff summarizes the long AYNA Academy conversation that happened before the work moved into the dedicated ChatGPT Project.

The goal is to prevent loss of context when Mariya opens a new AYNA Project session.

---

# People

## Mariya

Role:

- AYNA Domain Expert in training.
- Future Domain Architect.
- Learns skincare/cosmetic domain knowledge.
- Helps convert lessons into AYNA artifacts.
- No software background.
- Does not need to understand Git or Markdown deeply.

Working language:

- Russian is most comfortable for Mariya.
- She can use Turkish sometimes.
- When teaching Mariya, use Russian unless she switches language.

Important teaching note:

Mariya should not be overwhelmed with technical terminology.

Explain simply:

- Markdown = structured text file.
- Repository = AYNA’s official knowledge library.
- Artifact = approved AYNA knowledge card.
- Chat = temporary working session.

Mariya’s task is not to write code.

Mariya’s task:

1. Learn.
2. Ask questions.
3. Reason through cases.
4. Challenge weak logic.
5. Help define how AYNA should think.
6. Approve domain logic when she understands it.

---

## Korhan

Role:

- Product & Architecture.
- Created the Git repository.
- Created the ChatGPT Project named “Ayna”.
- Shared the project with Mariya.
- Connected a Google Drive folder containing the project files.
- Wants stable continuity across sessions.
- Wants AYNA artifacts to become the foundation for an AI Cosmetic Assistant.

Working language:

- Turkish is acceptable with Korhan.

---

# Project Setup Decisions

Korhan created a repository and added:

- `AYNA_OPERATING_MODEL.md`
- `knowledge_base/skin_biology/KB-0001_skin_barrier.md`

Later, the following files were created in the original session and should be added to the repository:

- `README.md`
- `AYNA_ARCHITECTURE.md`
- `AYNA_DESIGN_DECISIONS.md`
- `AYNA_KNOWLEDGE_ROADMAP.md`
- `AYNA_PROJECT_MEMORY.md`
- `AYNA_SESSION_BOOTSTRAP_PROMPT.md`
- `AYNA_SESSION_HANDOFF_2026-06-26.md`

Approved knowledge base artifacts that should also be added:

- `knowledge_base/skin_biology/KB-0002_tewl.md`
- `knowledge_base/ingredient_classes/KB-0003_humectants.md`
- `knowledge_base/ingredient_classes/KB-0004_emollients.md`
- `knowledge_base/ingredient_classes/KB-0005_occlusives.md`
- `knowledge_base/ingredients/KB-0006_petrolatum.md`

---

# Core Project Decisions

## 1. Repository artifacts are the source of truth

Chats are temporary.

Repository artifacts are canonical.

When chat history and repository disagree:

```text
Repository > Chat History
```

## 2. AYNA Academy and Product Intelligence Lab are separate

AYNA Academy:

- domain education
- reasoning
- knowledge artifacts
- rule design
- architecture decisions

AYNA Product Intelligence Lab:

- product teardown
- product review
- formula analysis
- marketing vs evidence
- product catalog metadata

## 3. Mariya’s education and AYNA knowledge creation are one process

Each lesson should eventually produce reusable AYNA knowledge when the concept is mature.

## 4. Trait ≠ State

Stable architectural decision.

Traits:

- long-term user characteristics
- change slowly

Examples:

- skin_type
- sensitivity_prone
- redness_prone
- product_tolerance_baseline

States:

- current skin conditions
- may change over days/weeks

Examples:

- barrier_damage
- dehydration
- irritation
- temporary_redness
- active_flare

## 5. User self-diagnosis is not final

User may say:

- “I have sensitive skin.”
- “I have allergy.”
- “I have rosacea.”
- “My barrier is damaged.”

AYNA should treat this as a signal, not a conclusion.

## 6. Clarification before recommendation

If symptoms include redness, burning, stinging, itching, swelling, new product reaction, possible allergy, barrier damage, or rosacea-like symptoms, AYNA should ask targeted questions before recommending.

## 7. AYNA must not diagnose

AYNA should not say:

> You have rosacea.

AYNA may say:

> Some symptoms may be consistent with rosacea-like skin reactivity. If frequent, persistent, or worsening, dermatologist evaluation is recommended.

## 8. Recommendations are risk-based and user-specific

A product is not simply good or bad.

Fit depends on:

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

# Completed Learning Cluster

## Barrier & Hydration Foundation

Approved artifacts:

- `KB-0001_skin_barrier.md`
- `KB-0002_tewl.md`
- `KB-0003_humectants.md`
- `KB-0004_emollients.md`
- `KB-0005_occlusives.md`
- `KB-0006_petrolatum.md`

Concepts learned:

- Skin barrier
- Stratum corneum
- Brick-and-mortar model
- Ceramides / cholesterol / free fatty acids
- TEWL
- Humectants
- Emollients
- Occlusives
- Petrolatum

Important conclusions:

- Barrier integrity affects hydration, sensitivity, irritation, and product tolerance.
- Humectants bring/hold water.
- Emollients smooth and soften.
- Occlusives reduce TEWL.
- Petrolatum is a highly effective occlusive, not inherently harmful.
- A moisturizer often works best when humectants, emollients, and occlusives are combined.

---

# Current Learning Module

## Sensitive Skin & Skin Reactivity

Status:

In progress.

The module is not ready for a final Approved artifact yet.

Expected major future artifact:

- `KB-0007_sensitive_skin.md`

This artifact should not be approved until consolidation.

Topics already discussed:

- Sensitive skin
- Redness-prone skin
- Contact dermatitis introduction
- Irritation vs allergy
- Fragrance and allergens
- Rosacea vs sensitive skin
- Barrier damage vs sensitive skin
- Clarification before recommendation
- Trait vs State

---

# Important Domain Learnings From Current Module

## Sensitive Skin

Sensitive skin is not a skin type.

It is better modeled as a trait:

```yaml
traits:
  sensitivity_prone: high
```

Key meaning:

- reduced product tolerance
- increased reactivity to cosmetic products
- frequent burning/stinging/discomfort after skincare

Sensitive skin is not automatically the same as:

- dry skin
- redness-prone skin
- barrier damage
- allergy
- rosacea

---

## Redness-Prone Skin

Redness-prone skin is separate from sensitive skin.

A user may flush after:

- wine
- heat
- hot showers
- stress
- emotions
- spicy food
- sun

while still tolerating cosmetic products well.

Example:

```yaml
traits:
  sensitivity_prone: low
  redness_prone: high
  vascular_reactivity: elevated
```

Important rule:

Not all redness equals sensitivity.

---

## Rosacea-like Symptoms

Rosacea is a chronic skin disease and outside AYNA's diagnostic scope.

AYNA should not diagnose rosacea.

AYNA can flag:

```yaml
medical_boundary:
  rosacea_suspected: possible
```

when the user reports some combination of:

- flushing after heat/alcohol/stress/sun
- persistent redness
- visible vessels
- papules/pustules
- eye symptoms

AYNA language must remain cautious.

---

## Barrier Damage vs Sensitive Skin

Barrier damage is a current state.

Sensitive skin is closer to a trait.

Example of barrier damage without true sensitive-prone trait:

```yaml
traits:
  sensitivity_prone: low

current_state:
  barrier_damage: true
  irritation: moderate
```

This may happen after overuse of:

- retinol
- AHA
- BHA
- scrubs
- harsh cleansers

Important reasoning pattern:

Before assuming sensitive skin, compare baseline vs current state.

---

## Irritation vs Allergy

Irritation pattern:

- burning
- stinging
- tightness
- dryness
- flaking
- often linked to actives/overuse/harsh cleansing

Allergy-like pattern:

- itching
- rash
- red patches
- swelling
- often after new product
- may be delayed

AYNA should use probabilistic language.

---

## Contact Dermatitis

Introduced but not fully consolidated.

Two relevant mechanisms:

1. Irritant Contact Dermatitis
2. Allergic Contact Dermatitis

---

## Fragrance & Allergens

Key points:

- Fragrance / Parfum / Perfume may hide many aromatic compounds.
- Fragrance is not automatically bad.
- Fragrance is a risk flag.
- Essential oils are not automatically safer because they are natural.
- For sensitivity-prone users, fragrance-free formulas usually have lower risk.

Important product logic:

```text
fragrance_present ≠ bad_product
fragrance_present = increased_risk_for_some_users
```

---

# Latest Case: Redness + Retinol Tolerance

Case:

User reports:

- face reddens after hot shower and glass of wine
- sometimes visible vessels near nose
- cosmetics usually do not sting
- retinol tolerated well

Corrected profile:

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

Why correction:

- No burning/stinging/flaking/pain, so irritation should be low.
- Visible vessels + flushing after heat/alcohol make rosacea-like reactivity possible, but not diagnosable.
- Good retinol tolerance argues against high sensitivity-prone trait.

Cosmetic recommendation:

- keep tolerated retinol if it does not worsen symptoms
- gentle cleanser
- daily SPF
- barrier-support moisturizer / ceramides
- avoid overuse of acids and harsh scrubs
- monitor triggers
- dermatologist if redness becomes persistent, inflammatory lesions appear, or eye symptoms occur

---

# Reasoning Patterns Observed From Mariya

Mariya is learning to think like AYNA.

Important patterns she demonstrated:

## 1. Ask before recommending

When user says “face red after cream,” Mariya asks:

- What other symptoms are present?
- Is there itching?
- Is there swelling?
- What is in the product?
- Was this reaction present before?
- What else was used in the routine?

## 2. Look for timeline

Mariya asks:

- Did it start after retinol?
- Did this exist before?
- Does burning happen after applying the product?

## 3. Compare baseline vs current state

Mariya reasoned that a person who never had product reactions before but damaged the barrier with actives should not be permanently labeled sensitive.

## 4. Separate redness from sensitivity

Mariya understood that flushing after wine/heat with good product tolerance is more redness-prone than sensitivity-prone.

## 5. Recognize safety signals

Mariya identified eyelid swelling as more concerning and more allergy-like than simple irritation.

## 6. Avoid overclaiming

Mariya often uses “more likely” reasoning instead of certainty, which matches AYNA safety boundaries.

---

# Current Next Steps

In the AYNA Project session, continue from:

## Sensitive Skin & Skin Reactivity consolidation

Recommended order:

1. Finish rosacea-like symptoms vs redness-prone vs sensitive skin.
2. Consolidate barrier damage vs sensitive skin.
3. Consolidate irritation vs allergy.
4. Finish contact dermatitis.
5. Finish fragrance/allergen risk.
6. Draft `KB-0007_sensitive_skin.md`.
7. Keep `KB-0007` as Draft until reviewed.
8. Update `AYNA_PROJECT_MEMORY.md`.

---

# Very Important Instruction For Future Assistant

Do not restart the course from the beginning.

Do not ask Mariya the original onboarding questions again.

Continue from the current module.

When working with Mariya, use Russian.

When working with Korhan, Turkish is acceptable.

If uncertain who is writing, infer from language and context or ask briefly.

The most important current objective is not to produce many files quickly.

The objective is to preserve quality and prevent premature artifacts.

Current guiding principle:

```text
Knowledge Quality > Knowledge Quantity
```
