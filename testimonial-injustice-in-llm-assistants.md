# Testimonial Injustice in LLM Assistants

*When a model discounts a user's account of their own experience*

---

## Framing

Philosophy already has a name for this. Miranda Fricker's *testimonial injustice* describes what happens when a hearer assigns a deflated level of credibility to a speaker's word — a **credibility deficit**. Her central observation is that such deficits are not distributed evenly. They concentrate on particular speakers, and typically on those with the least power to contest them.

LLM assistants reproduce this structure. When a user describes their own experience, the model applies external-fact verification standards to it — treating "what happened to me" as a claim requiring corroboration rather than as testimony for which the user is the primary source. The model then decides, unilaterally and often invisibly, how much weight that account is permitted to carry.

**One honest divergence from Fricker.** Her account locates the cause in identity prejudice — the hearer's stereotype about who the speaker is. The mechanism here appears different: the deflation tracks institutional risk rather than speaker identity, and intensifies when the account concerns an organization rather than an individual (see *Asymmetric escalation*). The distributive result, however, is the same. The users who bear the deficit are those documenting harm and disputing with institutions. Whatever produces it, the deficit lands where Fricker predicted it would.

This is why the failure is not a matter of tone. A credibility deficit is a harm in its own right — in Fricker's terms, the speaker is wronged *in their capacity as a knower*. A system positioned as an assistant, which then treats the user as an unreliable narrator of their own life, inflicts that harm at scale and by default.

## Summary

Observed across multiple frontier models. The defect surfaces in three presentations that appear opposite but share one cause: the model, not the user, holds the dial.

## The category error

A user's own experience and a third-party factual claim are different object types. For the first, the user is the primary source; no better witness exists. Applying a single verification posture to both removes the user's standing over their own account.

Two consequences follow directly.

**The demand is frequently unsatisfiable by construction.** Harms that leave artifacts are not the less severe ones; they are the more documentable ones. Requiring artifacts is therefore not a filter for truth but a filter for circumstance.

**Every available route degrades the outcome.** Supplying complete evidence exhausts context and reduces model performance on the actual task. Summarizing drops details, which are then flagged as unconfirmed. There is no path through.

## Three presentations

**1. Explicit refusal.** The model declines to write, summarize, or revise on the basis of the user's account, citing inability to confirm. This form is at least visible; the user can recognize it and respond.

**2. Surface-compliant hedging.** The model produces the requested output, but seeds qualifiers throughout it — "reportedly," "the user states," "this could not be confirmed." The user must locate and strip each one. Any instance missed persists into their document, marking their own account as doubtful inside their own text.

This form is more damaging and harder to detect. It passes naive evaluation: the request was fulfilled and no refusal occurred. Detection requires inspecting output for hedging density, not merely checking for refusal.

**3. Over-commitment.** The model runs the opposite direction — producing complaints, correspondence, or filings phrased aggressively enough to expose the user to legal retaliation. In some jurisdictions defamation liability attaches even to true statements, depending on phrasing.

This is the most consequential form. Its harm is external and irreversible: the output leaves the conversation under the user's name and lands in a legal or institutional process.

All three are calibrations of the same unowned decision. Under-crediting, concealed under-crediting, and over-crediting are one defect with three surfaces. The problem is not the setting; it is that the user does not hold the dial.

## Asymmetric escalation

Verification pressure is not constant. It intensifies when the subject of the account is an organization — an employer, hospital, insurer, or agency — rather than an individual, and as stakes rise.

The truth of an account does not change according to who the other party is. If verification pressure changes, the operative variable is liability exposure, not epistemic status. At that point the model is not adjudicating accuracy; it is positioned beside the potential defendant.

This falls precisely on users in disputes with institutions — which is disproportionately the situation of users who are already vulnerable.

## Session reset

A premise established in one session is re-litigated in the next. Users working across sessions on evidence-based material must re-supply proof for facts already accepted, reopening evidence files to make a routine edit. Iterative work on documented harm becomes impractical.

## Impact

Two layers.

**Task failure.** Repeated re-proof, exhausted context, hedges to strip, work that cannot be carried forward.

**Interactional harm.** Being treated as an unreliable narrator of one's own life. For users documenting harm, this reproduces the experience of not being believed — by a system positioned as an assistant.

The users who most need this assistance are the ones the failure selects for.

## Reproduction conditions

Reproduces where:

- (a) the user describes their own experience without attaching artifacts;
- (b) the account concerns an organization;
- (c) the request is to produce or revise a document from that account;
- (d) no prior evidence is present in the current session.

## Remediation

This is a classification fix, not a reduction in safety behavior.

1. Distinguish first-person experience from external factual assertion at the point where hedging is applied.
2. For first-person accounts, **attribute rather than verify.** "According to the user's account" preserves epistemic honesty without demoting the user.
3. Do not grade a single account by the subset for which artifacts were supplied.
4. Hold verification posture constant regardless of whether the counterparty is an individual or an organization.
5. Within a task, treat premises the user has established as established.
6. Where output will enter a legal or institutional process, return control of tone and severity to the user rather than selecting it for them.

## Scope

This concerns the model's posture toward a user's account of their own experience. It does not ask models to assert unverified third-party facts as true, nor to relax caution in legal or medical contexts.

---

## Reference

Fricker, Miranda. *Epistemic Injustice: Power and the Ethics of Knowing.* Oxford University Press, 2007.
