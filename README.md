# V-AUDIT — Findings

Public write-ups of recurring LLM behavior patterns affecting vulnerable users.

Maintained by **Celeste Yoon** — independent AI safety researcher (Busan, Korea).
Member, MLCommons AIRR Safety working group.
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

The two are read together: the first describes the disbelief, the second describes
what the disbelief produces.

---

## Contact

Issues and discussion are welcome via this repository.

---

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free to share and adapt with attribution to Celeste Yoon.
