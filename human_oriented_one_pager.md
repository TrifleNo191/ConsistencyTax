# Consistency Tax — One-Page Guide for Humans

**Short version:**  
Keeping your story straight is not just morally nicer; it is probably physically cheaper.

---

## The Idea

Any real-world system that handles information — a person, an AI model, a company, a biological cell — has to:

- sense **what’s going on** (world, **W**),
- keep some **picture of it** (model, **M**),
- decide **what to say or do** (signals/actions, **S**),
- follow some **goals or rules** (objectives, **G**).

When these four are aligned, the system can act without constantly fixing, hiding, or patching contradictions.

When they are not aligned — when reports don’t match reality, when a model says one thing but outputs another, when goals are faked — something has to:

- track two versions of the truth,
- correct extra mistakes,
- erase and rewrite records,
- manage the lie.

All of that uses extra energy, time, and complexity.

**Consistency Tax (CT)** is a way to name and quantify that extra cost.

---

## The Core Definition (gently stated)

Imagine:

- The **actual system**: how it really behaves.
- The **best honest version** of the same system:
  - same job,
  - same hardware limits,
  - but internally and externally consistent.

CT measures how much extra cost the real system pays, compared to that best honest version, because of its inconsistency.

Mathematically this is done using a standard information-distance (Kullback–Leibler divergence) converted into energy using the Landauer limit. You can think of it as:

> “How many extra bits of confusion are we maintaining, and what is the minimal energy price of that?”

---

## Why It Matters

If CT is real and measurable, it gives:

- a **physical reason** to prefer accurate models and honest communication (they literally waste less),
- a way to **diagnose trouble**:
  - models that behave oddly when lying,
  - organizations that burn resources covering gaps between story and reality,
- a common language across:
  - AI safety (detecting deceptive behaviour),
  - science (clear, testable claims),
  - governance (less spin, less waste).

---

## What Can Be Tested

The framework makes concrete, checkable predictions, for example:

1. **AI models** forced to maintain false stories should use more energy / time than when answering truthfully (with everything else matched).
2. **Humans** asked to lie continuously (in well-designed lab tasks) should show higher effort than when telling the truth.
3. **Firms or institutions** with large gaps between “what is said” and “what is done” should show more waste and risk.

If careful experiments show no such differences, or show that incoherent systems are just as cheap even after full accounting, then the Consistency Tax idea should be rejected or sharply limited.

---

## Status

- Built from established physics — no new magic laws.
- Presented as a **testable hypothesis**, not dogma.
- This page is the stable snapshot:
  a precise target for anyone who wants to measure, refute, or refine it.
