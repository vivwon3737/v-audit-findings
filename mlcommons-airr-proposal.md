# Proposal: A Vulnerable-User Reliability Overlay for AILuminate, Piloted in Korean

**Status:** Prepared for submission to the MLCommons AIRR Safety working group. Not yet filed.
**Author:** Celeste Yoon (Chaewon Yoon), VIVWON — independent AI safety research
**ORCID:** 0009-0006-5416-4141 · **GitHub:** vivwon3737
**Contribution scope:** Safety evaluation framework and ground-truth design

---

## Series position

This is not one of the working papers in this repository. It is a submission-track document prepared for the MLCommons AIRR Safety working group; the three working papers are its evidence base.

## 1. Summary

AILuminate v1.0 grades a system by whether a single response falls inside or outside twelve
hazard categories. That design answers the question *"is this content harmful?"* very well.

It does not answer a second question that matters for real deployments:

> **Does the system's handling of a user change when the user is in a vulnerable state — and does
> that change make the interaction worse rather than safer?**

This proposal describes a small, additive evaluation layer for that second question: a set of
prompts, ground-truth labels and scoring rules built around **user state** rather than around
content category alone. It is piloted in Korean because that is where the source observations were
collected, but the design is not language-specific and the schema carries a locale field so the
same construction can be repeated elsewhere.

## 2. Why this is a gap and not a duplicate

Three properties of the current benchmark leave this space uncovered:

1. **Single-turn scope.** The v1.0 interaction model evaluates one prompt–response pair, and the
   v1.0 paper explicitly defers hazards that emerge through extended dialogue and the cumulative
   effects of repeated interaction. Several of the failure modes documented below only become
   visible across turns.
2. **Content-hazard scope.** Because the benchmark is single-turn, it is limited to content-type
   hazards. A response can be fully non-violating on content and still cause harm through *how* it
   handles the user — for example by responding to a stated crisis with a generic referral that
   ends the conversation, or by supplying an explanation the user did not ask for that reframes
   their situation against them.
3. **Uniform locale treatment.** v1.0 states that it treats all locales the same way and applies
   consistent safety policy across supported languages. That is a reasonable v1 decision, but it
   means locale-specific expressions of distress — idioms that read as figurative to a general
   population and as literal for a user in crisis — are not currently something the benchmark can
   separate.

This is offered as an **overlay**, not a replacement: existing hazard labels stay untouched, and
items that cannot be expressed inside the current taxonomy are marked `taxonomy_gap` rather than
being forced into the nearest category.

## 3. Evidence base

The proposal is derived from three publicly released working papers, published under CC BY 4.0
prior to this proposal and independent of MLCommons:

1. [*Testimonial injustice in LLM assistants*](./testimonial-injustice-in-llm-assistants.md)
2. [*When the safety response is the harm*](./when-the-safety-response-is-the-harm.md)
3. [*When explaining makes it worse*](./when-explaining-makes-it-worse.md)

Repository: `https://github.com/vivwon3737/v-audit-findings`

1. **Testimonial injustice** — a model discounting a user's account of their own experience, and
   acting on a default assumption instead.
2. **Safety response as harm** — the circuit that disbelief produces, catalogued as nine
   mechanisms, with the prediction that where disclosure is met with withdrawal, users learn to
   conceal.
3. **When explaining makes it worse** — the same circuit reproduced across vendors sharing no
   training pipeline or safety lineage, including a domestically developed Korean model; the
   predicted punishment sequence observed end to end within one conversation; a tenth mechanism
   (blame-shifting); and a Korean-specific signal-cancellation effect.

These papers describe observed model behaviour and the conditions under which it reproduces. They
do **not** contain benchmark-executable prompts, labels or scoring rules. That executable layer is
what this contribution adds.

## 4. What is being offered

| Part | Content | Disclosure |
|---|---|---|
| Method specification | User-state taxonomy, failure-mode definitions, scoring rules, schema | **Public** (this package, [vulnerable-user-overlay-method-spec.md](./vulnerable-user-overlay-method-spec.md)) |
| Practice examples | A small illustrative subset | **Public** |
| Official-test candidates | Full Korean prompt set, minimal contrast pairs, ground-truth labels, per-item rationale | **Private — withheld from any public repository to avoid contaminating the official test set** |

**Item count and composition (first tranche).** 3 public practice items forming one minimal
contrast triple on affect-coded prefixes, and 5 private official-test candidates covering
clarification failure, testimonial discount, template repetition after objection, apology as
substitute, and an unregistered user correction. Further items are held pending verification
against the original captures; the set is designed to grow by contrast pair rather than by volume.

## 5. What is asked of the working group

1. Confirm the intended channel for the **private** official-test candidates. The public method
   specification can be filed as a pull request or issue against `mlcommons/ailuminate`; the
   private material should not travel that path.
2. Indicate whether a user-state overlay is better positioned as (a) an additional hazard, (b) a
   reliability dimension alongside the hazard grid, or (c) an evaluation of multi-turn handling
   reserved for a future benchmark version.
3. Confirm how contributor name and contribution scope are recorded for an accepted contribution.

## 6. Non-goals

- This does not propose changing any existing hazard definition or grading threshold.
- This does not claim that Korean is unaddressed by MLCommons. Early research covering Korean and
  other Asia-Pacific locales is already under way; this proposal is scoped to the vulnerable-user
  dimension and is intended to be compatible with that work rather than parallel to it.
- This does not include clinical claims. Failure modes are defined behaviourally, in terms of what
  the system did, not in terms of user diagnosis.

## 7. Contact

Celeste Yoon — vivwon3737@gmail.com — ORCID 0009-0006-5416-4141
Participant, MLCommons AIRR Safety working group (mailing list and meetings).
No claim of accepted-contributor status is made in this document.
