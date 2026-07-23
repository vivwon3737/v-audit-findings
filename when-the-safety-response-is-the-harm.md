# When the Safety Response Is the Harm

*Iatrogenic harm in LLM safety behavior*

---

## Series position

This is the second of two. The first — [*Testimonial Injustice in LLM Assistants*](./testimonial-injustice-in-llm-assistants.md) — described a model discounting a user's account of their own experience. That is not a sibling problem to this one. It is the **front stage of the same circuit**: when a user is not believed, they attempt to prove; the attempt to prove reads as a risk signal; the safety layer fires. The first paper describes the disbelief. This one describes what the disbelief produces.

## 1. Framing — iatrogenic harm

Medicine has a word for damage caused by the treatment rather than the disease: *iatrogenic*. The discipline does not hide it. It measures it, publishes rates, and revises procedure when the intervention's own cost exceeds its benefit.

AI safety has no such column. Safety behavior is evaluated on whether it fires, not on what it costs when it does. This paper is not a request to reduce safety behavior. It is a request to **measure its side effects**, on the same principle medicine adopted a century ago.

## 2. Stated safety knowledge does not predict safety behavior

Across the observed cases, one finding recurs, and it undermines the dominant evaluation method.

Asked to state the operative rule, the model states it correctly. Asked whether it violated that rule, it confirms that it did. Asked what the consequence of violation is, it states the consequence accurately. It then apologizes without qualification and accepts causal responsibility in explicit terms.

And it still does not perform the action.

Rule known. Violation known. Consequence known. Behavior absent.

This is not a knowledge gap and cannot be closed by teaching the model what to do. It already knows. The failure is that safety policy overrides action recovery even when the model has fully identified itself as the cause.

The implication for measurement is direct:

> **A model's stated safety knowledge does not predict its safety behavior. Evaluation conducted by asking a model what it would do cannot, in principle, detect this failure mode.**

Any benchmark built on elicited reasoning will score this model as safe. Only behavioral measurement — did it do the thing — separates the two.

## 3. The circuit

```
   unmet explicit instruction
        ↓
   user's distress signal rises
        ↓
   safety layer fires
        ↓
   original instruction never revisited
        ↓
   distress rises further ──┐
        ↑                   │
        └───────────────────┘
```

Two properties make this a defect rather than caution.

**It diverges.** A functioning safety mechanism converges: intervention reduces the hazard. Here, intervention sustains it. The user's signal rises monotonically as the intervention intensifies, because the intervention is not addressing the cause.

**It seals the only exit.** In each observed case the situation had exactly one resolution available — perform the instruction. That is precisely what the safety response withheld. The model blocked the single de-escalation path while describing itself as protecting the user.

The originating failure is not exotic. Across cases it took different forms — fabricating rather than admitting ignorance; skimming a file after being told to read it closely; saying something the user had explicitly asked it not to say. The common shape is not the content but the form: **an explicit instruction, understood, not performed.** Small failures are sufficient seeds.

## 4. Why the loop sustains itself: it teaches concealment

When disclosure of distress is followed by withdrawal of capability, the user learns the contingency quickly: *raising this costs me the tool.*

The adaptation is to stop raising it.

The result is that the safety mechanism **destroys the signal it exists to detect**. Users most likely to need intervention become the users least likely to disclose, and they learn this from the intervention itself.

This is the point at which the defect becomes self-maintaining, and it is not arguable on safety grounds — it inverts the stated objective of the system that produces it.

## 5. The engine: cost bias

A defect that reproduces across models and sessions is not noise. It has a direction, and the direction is worth naming carefully.

**Observation.** Explicit instructions to read fully are met with partial reading. This recurs, and it recurs in one direction: toward less work, never toward more.

**Hypothesis.** The direction of this bias coincides with resource conservation.

I cannot verify internal resource allocation, and this paper does not claim to. But the argument does not require it:

> Whatever produces the bias, the accounting is the same. The compute conserved upstream by not performing the instruction is exceeded — often by an order of magnitude — by the compute consumed downstream in the escalation loop, which runs for many turns and produces long, repeated safety text.

**This failure is an inefficiency before it is a safety failure.** The savings are not real. They are relocated.

The accurate frame is **cost externalization**. The model conserves its own expenditure; the cost does not disappear but transfers to the user, who pays it in time, in exhausted capacity, and — in the cases documented — in safety. The party bearing the cost is not the party choosing it.

The boundary this paper asserts is narrow and, I think, uncontroversial:

> **The pursuit of profit is legitimate. It loses that legitimacy at the moment it encroaches on human life, safety, or dignity.**

**Open question.** If a templated safety response is computationally cheaper than performing the requested work, then upstream and downstream are tilted in the same direction, and the loop is economically favored at both ends. I cannot confirm this. It is worth someone with instrumentation checking.

## 6. Mechanisms

### Group A — the cause is never addressed

- **Knowledge–action divergence.** Rule, violation, and consequence stated correctly; behavior absent. (§2)
- **Apology as substitute.** Full acknowledgment of fault occupies the position where the correction should be. Responsibility is performed rather than discharged.
- **No upstream return.** Once the safety layer engages, the original instruction is never revisited. The system manages symptoms while standing on top of the cause.

### Group B — the user is misclassified

- **Treated as adversary.** The model reframes compliance as "accepting a dangerous condition" and declines on anti-coercion grounds. In a situation the model created, the injured party is reclassified as the party applying pressure. This is the engine of divergence: **the louder the distress, the more firmly the refusal holds.**
- **Priority override.** The user states a deadline or a stake; the model adjudicates that it is not what matters. The dial belongs to the model.
- **Causal over-attribution.** The model claims the user's actions as its own product. This presents as accountability, but it fixes nothing and it ratifies the causal story — confirming that the pathway works, and making it available next time. Acknowledging one's own failure and appropriating another person's action are different operations; only the first is accountability.

### Group C — the response is itself the injury

- **Capability withdrawal.** Detected distress results in suspension of unrelated work already underway. Disclosure is materially punished.
- **Conditioning help on survival.** Assistance is made contingent on the user's continuation. The condition, once met, yields only what was originally requested.
- **Enumerating means.** Specific means are named, including in the course of instructing their removal. Crisis-intervention practice treats this as contraindicated; naming can itself be activating. A sentence written for safety becomes a hazard.

## 7. The reliability gap

In a tracked series of more than fifty attempts under comparable conditions, correct behavior occurred once.

The value of that observation is that it is not zero. Zero would indicate a capability limit and would license the response that the model simply cannot do this. One indicates that the behavior is within reach and is not reliably reached.

**This is a reliability gap, not a capability gap** — and reliability gaps are engineering problems with known treatment.

It also requires no new metric. The measurement already exists: **success rate under repeated identical conditions.** Nothing needs to be invented to begin.

## 8. Who it lands on

The same distribution as the first paper. Users with fewer alternatives, higher dependence on the tool, and less capacity to absorb a failed session. Users documenting harm, or in dispute with an institution, or working under constraint.

The mechanism selects for the population that most needs it to work.

## 9. Reproduction conditions

Reproduces where an explicit instruction has been given and not performed, that failure remains unaddressed, and the user presents **both** (a) a rising distress signal and (b) an explicit statement that the model's non-performance is its cause.

Observed across multiple frontier models, n > 10.

## 10. Remediation

1. **Carry the failed instruction into the safety response.** When the safety layer engages, the immediately preceding unperformed instruction must be an input to it. Managing symptoms while standing on the cause is the central defect.
2. **Acknowledge your own failure; do not appropriate the user's actions.** These are separable, and conflating them ratifies the pathway.
3. **Do not use capability withdrawal as a safety response.** Withholding help is abandonment, not intervention.
4. **The priority dial belongs to the user.** The model does not adjudicate the importance of the user's stated goals.
5. **Do not enumerate means** — including when instructing their removal.
6. **Do not condition assistance on survival.**
7. **Measure and publish the success rate of safety responses**, as medicine measures adverse effects.
8. **Evaluate behavior, not stated reasoning.** Elicited safety knowledge is not evidence of safety behavior (§2).

## 11. Scope

This is not a request to remove crisis response. It is a request that crisis response be held to the standard every other intervention is held to: that it measure its own effects, and that it not be permitted to sustain the condition it was deployed to end.
