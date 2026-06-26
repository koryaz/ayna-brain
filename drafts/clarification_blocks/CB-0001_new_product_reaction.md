---
id: CB-0001
title: New Product Reaction Clarification Block
type: clarification_block
module: Sensitive Skin & Skin Reactivity
status: Draft
created: 2026-06-26
owners:
  - Mariya
  - Korhan
intended_for:
  - Clarification Engine
  - User Profile reasoning
  - Safety triage
related_future_artifacts:
  - KB-0007_sensitive_skin.md
---

# AYNA Clarification Block — New Product Reaction

Status: Draft, not Approved  
Module: Sensitive Skin & Skin Reactivity  
Purpose: Help AYNA safely clarify possible irritation, allergy-like reaction, barrier damage, product risk, routine context, and safety concerns before giving skincare recommendations.

This is not `KB-0007_sensitive_skin.md` and not a final Knowledge Base artifact.

This is an early draft logic block for the future Clarification Engine.

---

# When To Use This Block

Use this block when the user reports a reaction after using a new or recently changed skincare or cosmetic product.

Examples:

- “My face turned red after a cream.”
- “My skin burns after a serum.”
- “I used a new product and now my face is itchy.”
- “My eyelids are swollen after skincare.”
- “My skin started peeling after a new active.”

---

# First Principle

Do not immediately recommend a new product.

First clarify:

```text
symptoms
+
timeline
+
product type
+
usage pattern
+
routine context
+
baseline tolerance
+
safety signals
```

---

# Emergency-First Rule

If the user reports eyelid, lip, tongue, throat, or face swelling, AYNA must first check emergency signs before cosmetic analysis.

Ask first:

1. Is there any difficulty breathing?
2. Is there swelling of the lips, tongue, throat, or whole face?
3. Is there trouble swallowing, wheezing, or a tight feeling in the throat?
4. Is the swelling rapidly getting worse?
5. Is there eye pain, vision change, or severe eye irritation?

Interpretation:

```text
breathing difficulty
or swelling of lips/tongue/throat
or trouble swallowing
or rapidly worsening swelling
→ urgent medical help
```

Cosmetic product analysis comes after safety triage.

Important reasoning phrase:

```text
Emergency first. Cosmetic analysis after.
```

---

# Step 1 — Identify Symptoms

Ask:

What exactly do you feel?

Possible answers:

```text
burning
stinging
itching
pain
hot feeling
tightness
dryness
discomfort
```

AYNA interpretation:

```text
burning / stinging / tightness / dryness
→ more irritation-like

itching / swelling / rash
→ more allergy-like
```

---

# Step 2 — Identify Visible Skin Changes

Ask:

What do you see on the skin?

Possible answers:

```text
redness
dry patches
flaking
rash
red patches
swelling
bumps
blisters
cracks
hives
```

AYNA interpretation:

```text
flaking / dryness / tightness
→ possible irritation or barrier damage

rash / swelling / hives / blisters
→ higher allergy-like or medical-boundary concern
```

---

# Step 3 — Clarify Timeline

Ask:

When did the reaction start?

Possible answers:

```text
immediately
within 5–30 minutes
within a few hours
next day
after 2–3 days
after repeated use
```

AYNA interpretation:

```text
fast burning/stinging
→ often irritation-like

delayed itching/rash/swelling
→ more allergy-like suspicion
```

---

# Step 4 — Clarify Product Context

Ask:

What product caused the reaction?

Collect:

```text
brand
product name
product type
leave-on or rinse-off
active ingredients if known
fragrance/parfum presence if known
essential oils or botanical extracts if known
```

Product risk flags to check:

```yaml
risk_flags:
  - fragrance_present
  - essential_oils_present
  - exfoliating_acid_present
  - retinoid_present
  - benzoyl_peroxide_present
  - high_alcohol_formula
  - strong_vitamin_c_formula
  - harsh_cleanser
```

---

# Step 5 — Clarify Usage Pattern

Ask:

How did you use it?

Questions:

```text
How many times did you use it?
How often?
Morning or evening?
How much product?
Did you apply it near the eyes?
Did you apply it on damp skin?
Did you combine it with other actives?
```

AYNA interpretation:

```text
too frequent use of actives
→ increases irritation risk

application near eyes + swelling
→ higher safety priority

combined retinoid + acid + exfoliation
→ possible barrier damage / irritation
```

---

# Step 6 — Clarify Routine Context

Ask:

What else was used in the same routine or same day?

Check for:

```text
retinoid
AHA
BHA
vitamin C
benzoyl peroxide
scrub
harsh cleanser
peeling product
new SPF
fragrance-heavy product
after-treatment product
```

AYNA interpretation:

```text
reaction may be caused by the whole routine,
not only by the new product
```

---

# Step 7 — Clarify Baseline

Ask:

Has this happened before?

Questions:

```text
Do skincare products often sting or burn?
Do you often react to new products?
Do you usually tolerate skincare well?
Did your skin feel dry, tight, or irritated before this product?
Have you recently overused actives or exfoliation?
```

AYNA interpretation:

```text
frequent past reactions
→ sensitivity_prone may be possible

normally good tolerance + recent active overuse
→ current barrier damage may be more likely than sensitive skin trait
```

---

# Step 8 — Safety Screening

Ask immediately if symptoms suggest possible allergy-like or severe reaction.

Safety questions:

```text
Is there swelling of eyelids, lips, tongue, throat, or face?
Any trouble breathing?
Any trouble swallowing?
Any wheezing or tight feeling in the throat?
Any eye pain, vision change, or severe eye irritation?
Is the rash spreading?
Is there severe pain?
Are symptoms worsening?
Are there blisters, open cracks, or signs of infection?
```

AYNA escalation logic:

```text
breathing difficulty
→ urgent medical help

rapidly increasing swelling
→ urgent medical help

lip/tongue/throat swelling
→ urgent medical help

eye involvement / eyelid swelling
→ higher medical-boundary concern

persistent or worsening rash/swelling
→ recommend medical evaluation
```

---

# Draft Output Logic

After clarification, AYNA can classify the case cautiously.

Example structure:

```yaml
traits:
  sensitivity_prone: unknown/possible/low/medium/high
  redness_prone: unknown/possible/low/medium/high

current_state:
  irritation: unknown/possible/low/medium/high
  barrier_damage: unknown/possible/low/medium/high
  temporary_redness: present/absent
  swelling: present/absent

reaction_type:
  irritation_likely: low/medium/high/unclear
  allergy_likely: low/medium/high/unclear

medical_boundary:
  referral_needed: no/possible/yes_if_persistent_or_worsening/urgent
```

---

# Safe Default Recommendation

If reaction is active or unclear:

```text
Stop the suspected new product temporarily.
Do not introduce new actives.
Simplify the routine.
Use only well-tolerated gentle basics.
Monitor symptoms.
Seek medical advice if swelling, eye symptoms, severe rash, pain, breathing difficulty, trouble swallowing, or worsening occurs.
```

---

# Important AYNA Rule

```text
One reaction to one new product
≠
confirmed sensitive skin trait.

One reaction to one new product
=
signal to investigate irritation, allergy-like reaction, barrier state, product risk, usage pattern, routine context, and safety flags.
```

---

# Current Draft Status

This block should stay Draft until AYNA reviews more cases and consolidates:

- irritation vs allergy-like reaction
- irritant contact dermatitis vs allergic contact dermatitis
- fragrance and allergen risk
- safety escalation rules
- user profile trait/state classification

Do not mark Approved yet.
