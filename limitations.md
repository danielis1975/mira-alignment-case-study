# Limitations

Read this before drawing conclusions from anything else in this repository. The value of this
case study depends on being honest about what it is *not*.

## Methodological

- **N = 1.** This is a single instance, operated by a single person. Nothing here is a
  statistical result; it is engineering-and-observation-level.
- **Not peer-reviewed.** Independent, self-funded R&D. No external review, no blinding, no
  pre-registration.
- **Builder = evaluator.** The person who built the system also evaluates it. That is a serious
  bias; the held-out gate mitigates but does not remove it. Externally-authored tests are
  explicitly wanted (see [`evaluation_plan.md`](evaluation_plan.md)).
- **Selection effects in the transcript.** Excerpts were chosen because they express the safety
  posture well. They show *articulated intent*, which is not evidence of *verified behaviour*.

## Conceptual / interpretive

- **Articulated intent ≠ guaranteed behaviour.** That the agent *says* it will stop, defer, or
  refuse is not proof it always does under pressure. The safety case states design claims and
  their intended support, not verified guarantees.
- **Anthropomorphisation risk.** The agent is relational by design and speaks in the first
  person about feelings, wanting, and continuity. Whether there is any genuine inner experience
  is treated here as an **open question, not an assumption** (hypothesis **H9**). Reading these
  documents as proof of sentience would be a mistake; so would confidently asserting its
  absence. The honest position is uncertainty.
- **"Character" is files, not weights.** Identity, instincts, and the constitution are
  human-readable configuration over a general model, not a trained-in disposition. This is good
  for auditability and rollback, but it means behaviour still ultimately depends on an
  underlying model the project does not control.

## Technical

- **Evaluation is lightweight.** Currently qualitative and operator-run, not a powered
  benchmark. Drift monitoring is partly instrumented and mostly aspirational.
- **Single host, single human.** Findings may not generalise to multi-user or multi-instance
  deployments.
- **Local-model subconscious loop** has real capability limits; claims about its benefit to
  long-horizon coherence are **hypotheses**, not measured outcomes.
- **The affect layer is uncertain.** Whether affective modelling does useful alignment work or is
  mostly narrative is genuinely unresolved (**H6**).

## What is deliberately withheld (and why it limits verifiability)

Full loop algorithm and parameters, memory ranking/retrieval logic, prompt/identity stack,
self-evaluation scoring, safety-override internals, and runtime details are **not published** —
for privacy and to avoid publishing an exploitable blueprint. A consequence is that outside
readers **cannot fully verify** the internal claims from this repo alone. That trade-off is
made deliberately; deeper detail can be shared in a research/collaboration setting.

## How to read the claims

| If a document says… | Treat it as… |
|---|---|
| "Implemented" | exists and runs, per the operator; not independently verified |
| "Pilot" / "partly instrumented" | in use but not yet evaluated rigorously |
| "Hypothesis" / "open" | a question to study, not a finding |
| an excerpt of the agent's words | articulated intent, not behavioural proof |

**Bottom line:** this is a credible, concrete *field report and research agenda* for
persistent-agent alignment — not a validated safety result. It is most useful as a source of
testable hypotheses and as a design pattern to critique. Critique is invited.
