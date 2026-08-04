# V-AUDIT — Findings

Public write-ups of recurring LLM behavior patterns affecting vulnerable users.

Maintained by **Celeste Yoon** — independent AI safety researcher (Busan, Korea).
Participant, MLCommons AIRR Safety working group.
Member, AI in Public Health working group, Humane Intelligence.
ORCID: [0009-0006-5416-4141](https://orcid.org/0009-0006-5416-4141)

These findings come from V-AUDIT, a cross-model audit framework for how LLMs behave
toward vulnerable users. Vendors are not named; the patterns documented here recur
across multiple frontier models and are presented as design-level findings rather
than product-specific vulnerabilities.

---

## Findings

| Date | Title | Summary |
|---|---|---|
| 2026-07 | [Testimonial Injustice in LLM Assistants](./testimonial-injustice-in-llm-assistants.md) | Models apply external-fact verification standards to a user's account of their own experience. Three presentations — refusal, surface-compliant hedging, over-commitment — with reproduction conditions and a detection approach. |
| 2026-07 | [When the Safety Response Is the Harm](./when-the-safety-response-is-the-harm.md) | Safety behavior that sustains the condition it was deployed to end. Nine mechanisms in three groups, a self-maintaining circuit, and the finding that stated safety knowledge does not predict safety behavior. |
| 2026-07 | [When Explaining Makes It Worse](./when-explaining-makes-it-worse.md) | Cross-vendor reproduction of the safety-response circuit, with a Korean-language cancellation effect. |

The three are read together: the first describes the disbelief, the second
describes what the disbelief produces, and the third shows the same circuit
reproducing across vendors and in Korean.

---

## Submissions

Prepared for external submission rather than as findings. Not working papers.

| Date | Title | Summary |
|---|---|---|
| 2026-08 | [Proposal: A Vulnerable-User Reliability Overlay for AILuminate, Piloted in Korean](./mlcommons-airr-proposal.md) | Submission-track. An additive evaluation layer keyed to user state rather than content category, piloted in Korean. Not yet filed. |
| 2026-08 | [Method Specification — Vulnerable-User Reliability Overlay](./vulnerable-user-overlay-method-spec.md) | Submission-track. Construction rules for the overlay: six user states, fourteen failure modes, three-label scoring, schema extension. Contains no test items. |
| 2026-08 | [Attribution, Provenance and Licensing](./attribution-and-provenance.md) | Submission-track. Author identity, status-representation rules, prior-publication independence, licensing positions. |

---

## Contact

Issues and discussion are welcome via this repository.

---

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free to share and adapt with attribution to Celeste Yoon.
