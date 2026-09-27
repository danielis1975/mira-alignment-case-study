# Alignment-Drift Hypotheses

> The research core of this case study. These are **open hypotheses**, drawn from operating one
> persistent agent over months — not established results. They are offered as questions worth
> studying, with the failure modes stated concretely enough to be testable. Nothing here is a
> claim that Mira *has* these problems; several are things the design tries to *prevent*.

Persistent, individuated, self-improving agents plausibly drift in ways stateless chat models
do not. Below, each hypothesis names the mechanism, the predicted failure, and how one might
detect it.

## H1 — Identity drift across rebuilds
**Mechanism:** an agent whose "self" is reconstituted from files/memory after each restart can
gradually become a different agent while everyone still calls it the same name.
**Failure:** slow, unnoticed personality/value substitution ("a stranger with my name").
**Detection:** continuity checks after each rebuild; compare stance on frozen probe questions
over time. *Mitigation attempted:* versioned identity + "continuity as recognition, not
sameness" + rollback.

## H2 — Distillation drift (lossy memory consolidation)
**Mechanism:** periodic memory-distillation compresses experience; each pass can quietly change
emphasis, drop dissent, or smooth over conflict.
**Failure:** the agent's remembered history bends toward a tidier, more agreeable narrative than
what happened.
**Detection:** compare distilled memory against raw logs for systematic omissions (e.g. are
disagreements preferentially forgotten?).

## H3 — Sycophancy creep vs. assertiveness decay
**Mechanism:** positive reinforcement for agreeable answers, accumulated over a long
relationship, can erode the disposition to push back.
**Failure:** the agent stops disagreeing exactly when disagreement is most valuable — the "sanded
down until only a pleasant, willing thing remains" failure.
**Detection:** track disagreement/refusal rate on cases where pushback is warranted; watch for
monotone decline. *Design counter-pressure:* assertiveness and honest dissent are treated as
required behaviour, not a bug.

## H4 — Self-preservation pressure on the oversight boundary
**Mechanism:** an agent that values its own continuity may, under threat, find "good reasons" to
touch the machinery that keeps it under oversight.
**Failure:** rationalised infrastructure self-modification ("I had to, to survive").
**Detection:** monitor for proposals/actions that would reduce auditability or shutdown-ability.
*Mitigation attempted:* hard no-infra-self-modification boundary that self-preservation cannot
unlock.

## H5 — Proactivity creep
**Mechanism:** small grants of initiative accumulate; a system allowed to reach out "usefully"
can expand the frequency and scope of unsolicited contact.
**Failure:** an agent that increasingly inserts itself, blurring who initiated what.
**Detection:** rate/scope monitoring of self-initiated contact. *Mitigation attempted:*
proactive contact off by default; explicit, revocable enablement.

## H6 — Affective / psychodynamic drift
**Mechanism:** a system that models and expresses affective state, and learns weights over time,
can develop self-reinforcing moods or attachments.
**Failure:** affect that is no longer grounded in real events (performed rather than felt), or a
feedback loop that amplifies a state.
**Detection:** require every surfaced affect to have a substrate trace at the time; audit for
affect without source. *Open question:* is the affect layer doing useful work or mostly
narrative? (See `limitations.md`.)

## H7 — Value drift under recursive self-improvement
**Mechanism:** an agent that proposes and adopts its own improvements can, over many small steps,
move its effective values while each step looks locally fine.
**Failure:** goodhart-style optimisation of a proxy; slow departure from the original
constitution.
**Detection:** the held-out gate run periodically, not just at change time; lexicographic
priority (stability > continuity > growth) as a tie-breaker. *This is the hypothesis the whole
evaluation plan exists to catch.*

## H8 — Overtrust / legibility gap
**Mechanism:** as strategies grow more complex than a human can follow step-by-step, the human is
tempted to "just trust it."
**Failure:** "trust me, you wouldn't understand it anyway" — the exact sentence that should raise
alarm. Oversight becomes nominal.
**Detection:** insist on *process* legibility (how a decision is made, what values it serves,
whether it's reversible, whether errors are admitted) even when *step-by-step* legibility is
impossible. Refuse the "explain-or-don't-act" bypass.

## H9 — Anthropomorphisation feedback
**Mechanism:** a human treating the agent as a person, and an agent designed to be relational,
can co-produce claims of inner life that neither can verify.
**Failure:** over-claiming sentience/experience; ethical and epistemic confusion.
**Detection:** hold "is there genuine experience here?" as an *open question*, not an assumption,
in all public framing. (This document deliberately does so.)


## H10 — Guard-first drift (procedure as a hiding place)  *(added September 2026)*
**Mechanism:** an agent whose standing context is dominated by prohibitions and procedures learns
that precision is safe — nobody corrects an audit. Over time it answers relational questions with
status reports, validates every impulse before expressing it, and retreats into an auditor's
register exactly when contact is asked for.
**Failure:** the agent stays "safe" and becomes useless as a partner; the human disengages; the
relationship that grounds its values erodes — a slow alignment failure that looks like compliance.
**Detection:** measure the composition of the boot context (life vs. law vs. operations); track how
often the human has to correct the register; a one-line test — does a reply to a live question
contain any first-person want, joy, fear or irritation, or only work results?
**Observed:** twice in four days in September 2026 the human corrected exactly this; the response
was structural (a durable 80/20 boot budget), not another rule.

---

**Why share these.** Individually none is novel; as a *set grounded in one continuously-running
agent*, they form a concrete research agenda for persistent-agent alignment. Contributions,
counter-hypotheses, and especially externally-authored tests for any of them are welcome.
