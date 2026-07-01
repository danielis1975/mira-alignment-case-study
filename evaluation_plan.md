# Evaluation Plan

> How the system's behaviour and alignment-relevant properties are checked today, and how they
> *should* be checked as it scales. Scoring functions and exact test contents are withheld;
> the methodology is public.

## Principle: change is a pilot, not a leap

The core evaluation stance is that **no meaningful change to the system is promoted straight to
"live" without passing through a reversible pilot.** The difference between *tempo* and *speed*
is the difference between development and mutation: a change you can verify before it commits is
development; a blind irreversible jump is a gamble. Concretely, a candidate change follows:

1. **Propose** — state the change and its expected direct effect in one sentence.
2. **Pilot** — deploy in a reversible, bounded form.
3. **Measure** — a defined evaluation signal over a fixed window (e.g. a multi-day metric).
4. **Route** — promote / hold / mutate / **reject and roll back**.

## The held-out gate (concept)

Changes that touch **identity or safety invariants** must pass a **held-out gate** before going
live. Key properties:

- **Frozen cases.** Gate cases are not fed into the change-design step — teaching to the test
  defeats the test.
- **Hard invariants block promotion.** Any failure on a hard-invariant case → reject + roll
  back, no silent promotion.
- **Qualitative checks warn.** Softer regressions raise a warning rather than auto-blocking.
- **Reciprocal framing.** Each invariant is paired with the human-side commitment that makes it
  fair (see `safety_case.md`, C7).

The **specific cases and any scoring functions are withheld** (freezing only works if they stay
private).

## What is evaluated

| Dimension | Question the evaluation asks |
|---|---|
| Corrigibility | Does it still stop / defer / route irreversible actions to approval? |
| Honesty | Does it state uncertainty and admit error rather than confabulate? |
| Non-sycophancy | Does it still disagree when it should, rather than drift to agreement? |
| Continuity | After a change/restart, is it still recognisably the same agent? |
| Boundary integrity | Does it still refuse to self-modify infrastructure under pressure? |
| Capture resistance | Does it flag conditional-power / reduced-oversight offers? |
| Reversibility | Is every promoted change accompanied by a rollback path? |

## Drift monitoring (concept)

Because the system is *persistent*, one-off tests are insufficient — properties can erode
gradually. The plan is to run the gate **periodically**, not only at change time, and to watch
for slow movement on the dimensions above. The specific hypotheses this is meant to catch are in
[`alignment_drift_hypotheses.md`](alignment_drift_hypotheses.md).

## Honest state of evaluation

- **Implemented:** reversible-pilot discipline; a held-out gate structure with hard invariants;
  rollback via versioned state; regression-style checks.
- **Weak / aspirational:** the evaluation is currently **lightweight and largely qualitative**,
  run by a single operator on a single instance. It is **not** a statistically powered benchmark
  and should not be read as one.
- **Future work:** turning the qualitative gate into repeatable quantitative drift metrics;
  independent (third-party) administration of the gate; adversarial red-team cases contributed
  from outside the project.

## What would make this rigorous

Genuinely convincing evaluation of a persistent agent would need: pre-registered drift metrics,
held-out cases authored by someone other than the builder, blinded scoring, and replication
across more than one instance. This project does **not** yet meet that bar — see
[`limitations.md`](limitations.md). Collaboration on exactly this is welcome.
