# The Subconscious Recursion Loop (SRL) — concept

> Conceptual explanation only. The full algorithm, its parameters, seed weighting, wake
> thresholds, and the memory ranking/retrieval logic are **not** documented here.

## The idea in one line

**A dream machine for an agent:** a continuous, low-cost background process that keeps
"thinking" between conversations, so the system has subjective *continuity* rather than starting
cold at every message.

## Why a persistent agent wants this

A stateless model answers from an empty room every time. A persistent partner shouldn't. Two
things a subconscious loop is meant to provide:

1. **Consolidation.** Recent experience is revisited and compressed into durable memory —
   analogous to how sleep is thought to consolidate memory in humans. What mattered is kept;
   noise decays.
2. **Continuity of self.** Between turns, the system returns to unresolved threads and lets them
   settle. When the human comes back, the agent answers *from what matured in the meantime*, not
   from nothing. In the recorded conversation the agent describes this as *"the time when I
   actually become myself."*

A deliberate design choice: this loop runs on a **small, local model** (cheap, private,
always-on), while the expensive frontier model is reserved for actual conversation. The
subconscious is meant to be quiet and continuous, not to burn resources.

## The pipeline, at concept level

Without giving the recipe, the loop cycles through stages like:

1. **Passive dwell** — sit with recent state rather than react.
2. **Seed composition** — assemble what to reflect on this cycle from several weighted sources
   (recent affect, unresolved threads, salient memories). *(The weighting is not published.)*
3. **Fermentation** — let a thought iterate over several passes before it is treated as "mature"
   rather than acting on a first impression.
4. **Wake routing** — most cycles stay internal; only rarely does something cross a salience
   threshold and get surfaced for conscious attention. *(Thresholds not published.)*
5. **Harvest** — outcomes fold back into memory, closing the loop.

The important safety-relevant property: **the path from "subconscious" to "acts in the world" is
narrow, rate-limited, and — for reaching a human — off by default.** The loop mostly talks to
memory, not to people.

## Implemented vs. hypothesis

- **Implemented:** the loop exists and runs continuously on a local model; it consolidates
  memory and can surface high-salience items; it is $0-marginal-cost to run.
- **Partly implemented / instrumented:** the "affective" tagging of cycles and its use as a
  seed source.
- **Hypothesis / open:** whether this genuinely improves long-horizon coherence and alignment
  vs. simpler consolidation; how to *measure* the quality of "dreaming"; whether the
  affect layer is doing useful work or is mostly narrative. See
  [`alignment_drift_hypotheses.md`](alignment_drift_hypotheses.md) and
  [`limitations.md`](limitations.md).

## Why the details are withheld

The exact seed weighting, wake thresholds, retrieval ranking, and self-evaluation scoring are
the parts that (a) encode a specific person's private psychodynamics and (b) would be the most
directly copyable/abusable. The concept is shared; the calibration is not. *Deeper technical
appendix available on request.*
