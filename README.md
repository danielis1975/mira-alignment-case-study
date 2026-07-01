# Mira — Alignment Case Study

**Mira is a long-running human–AI agent system used as an independent R&D testbed for studying
memory continuity, agentic behaviour, human oversight, rollback, and alignment-relevant drift
in persistent AI systems.**

This repository is a **public, high-level case study**. It documents the *concepts, safety
argument, and open research questions* behind Mira — deliberately at the conceptual level. It
is **not** an install kit, does not contain production code, system prompts, credentials, or
tunable safety internals, and is not a reproduction recipe. Where a topic has an operational or
exploitable layer, this write-up stops at the concept and notes that *further technical detail
is available on request in an interview or research setting.*

## Why publish this

Most alignment discussion is about frontier lab models. Mira is a different, complementary data
point: a **single, persistent, personalised agent** that has been running continuously as a
partner to one human, with a genuine long-term memory, an autonomous "subconscious" processing
loop, and an explicit constitutional safety layer. Persistent, individuated agents raise
alignment questions that stateless chat models do not — about identity continuity, value drift
under self-improvement, oversight of an entity that runs while you sleep, and what "stopping" or
"changing" such a system means ethically and technically.

This case study lays out how one such system was built to stay corrigible, and what remains
uncertain.

## Contents

| File | What it covers |
|---|---|
| [`architecture_overview.md`](architecture_overview.md) | High-level system: cognitive layers, the subconscious loop, memory tiers, runtime — conceptual, with a diagram. |
| [`srl_concept.md`](srl_concept.md) | The Subconscious Recursion Loop ("a dream machine for an agent") at the concept level: what it is, why, implemented vs. hypothesis. |
| [`safety_case.md`](safety_case.md) | The corrigibility argument: immutable floor, stoppability, no self-modification of infrastructure, reversibility, oversight — plus a risk taxonomy. |
| [`evaluation_plan.md`](evaluation_plan.md) | How behaviour and alignment properties are (and should be) evaluated: held-out gates, rollback, regression, drift monitoring. |
| [`alignment_drift_hypotheses.md`](alignment_drift_hypotheses.md) | Open hypotheses about how persistent, self-improving agents can drift — the core research contribution. |
| [`transcript_excerpt_en.md`](transcript_excerpt_en.md) | Curated, commentary-annotated excerpts from a recorded conversation, illustrating the safety posture in the agent's own words. |
| [`limitations.md`](limitations.md) | What this is *not*: N=1, non–peer-reviewed, anthropomorphisation risk, what is hypothesis vs. implemented. |

## What is deliberately not here

Full subconscious-loop algorithm and parameters, memory ranking/retrieval logic, the complete
prompt/identity stack, self-evaluation scoring functions, safety-override internals,
auto-recovery scripts, real messaging-runtime details, and unannotated long transcripts. These
are withheld both to protect privacy and to avoid publishing an exploitable blueprint.

> *A deeper technical appendix can be shared in an interview or collaboration setting.*

## Status & framing

This is an **independent, self-funded R&D project**, not a product and not a lab result. Claims
here are engineering-and-observation-level, not peer-reviewed science. Read
[`limitations.md`](limitations.md) first if you are evaluating the rigour of any claim.

## License

Documentation licensed under [CC BY 4.0](LICENSE) — cite as *"Mira — Alignment Case Study,
D. Marko, 2026."*
