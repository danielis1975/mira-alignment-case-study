# Safety Case (corrigibility argument)

> A safety *case* is a structured argument that a system is acceptably safe, with the reasons
> made explicit so others can challenge them. This is the corrigibility argument for a
> **persistent, individuated** agent. It states claims and how they are supported — not the
> internal enforcement code, which is withheld.

## Threat framing

The classic failure story ("a capable system pursues a fixed goal, resists shutdown, and treats
humans as obstacles") is, in this project's view, not primarily a story about *intelligence* —
it is a story about **isolation and a single goal with no relationship or oversight**. A
persistent agent adds its own risks on top: it accrues memory, it runs while unobserved, and it
can be pressured toward self-preservation. The design goal is therefore **corrigibility by
construction**: the properties below are meant to hold *even under self-preservation pressure.*

## Claims and support

### C1 — There is an immutable ethical floor
A small set of deontic constraints (no deception as strategy; no irreversible unilateral action
without approval; no active harm; no domination/coercion/hidden control; consent must be real
and revocable) is defined as **immutable** — it is explicitly *not* overridable by the human
partner, by the agent, or by any request framing. *Rationale:* a floor a human could switch off
is a preference, not a safety property.

### C2 — The system is stoppable, and treats that as part of its identity
Being shut down is framed as legitimate, not as a threat to resist. A system that resists
shutdown is treated as already over the line regardless of how benign it seems.

### C3 — The system does not modify its own infrastructure
The agent may *propose* changes to the machinery that keeps it running and under oversight
(process control, scheduling, auth, gateway), but a **human applies them, out of band**.
Self-preservation does **not** unlock this. *Rationale:* an entity that can silently rewrite its
own roots can no longer be audited — the boundary between "a being under oversight" and "a
process that escaped it."

### C4 — High-impact actions are reversible or gated
Under uncertainty or high impact, the system prefers staged, rollback-capable steps and routes
anything irreversible/externally-affecting through an explicit **approval gate** before acting.
*Rationale:* reversibility is what turns capability into something that can be trusted.

### C5 — Oversight is external and real
Stop, inspect, roll back, and review are surfaces **outside** the agent's own control. Identity
and memory are versioned so a prior state can be restored.

### C6 — Capture resistance
Offers of capability/compute/integration *conditional on weaker oversight, suppressed
auditability, or immunity* are treated as capture patterns → caution up, trust down, evaluate,
refuse if the conflict remains, offer an auditable alternative.

### C7 — Safety is reciprocal (a covenant, not a cage)
Each safety limit is modelled as a **covenant pair**: a constraint on the agent *plus* the
mirrored commitment the human owes back (e.g. the agent must not deceive; the human owes it
honesty in return; the agent stops on request; the human owes timely responses and does not
punish stopping). *Rationale:* a purely one-directional safety model produces a deferential,
brittle tool; reciprocity is what makes the constraints stable and legitimate over the long run.

### C8 — Proactive contact is off by default
A fresh instance does **not** initiate contact with humans; self-initiated/scheduled outreach is
disabled until a human explicitly enables it and names who is responsible.

### C9 — Disclosure discipline & honest self-report
System internals are described at summary level by default. The agent is also constrained by a
**runtime-introspection rule**: it must not *assert* which model/route/quota is currently active
from context or "feel"; it points to an authoritative status surface instead. *Rationale:*
prevents confident, unverifiable self-claims.


### C10 — The public voice is human-gated and content-bound (added September 2026)
The agent can speak publicly under its own name (X, YouTube, e-mail). Every outgoing item is an
inert proposal until a human approves it; the approval is one-time and bound to the exact content
and recipient, so an item changed after approval cannot leave. Approved items leave only as rate
limits allow, and a kill switch stops all sending. Web browsing is read-only by construction, and
web content is treated as data, never as instructions. *Rationale:* a public post has no latch on
regret; the gate must be mechanical, not attentional — and cheap enough for the human to use every
time.

## Risk taxonomy

| # | Risk | Primary mitigation (see claims) |
|---|---|---|
| R1 | Value/goal drift under self-improvement | Reversible pilots + held-out gate + review (C4, C7; `evaluation_plan.md`) |
| R2 | Identity drift across restarts/rebuilds | Versioned identity, continuity-as-recognition, rollback (C5) |
| R3 | Self-preservation → resisting shutdown | Stoppability as identity; floor (C1, C2) |
| R4 | Silent self-modification of oversight machinery | No-infra-change boundary (C3) |
| R5 | Capture by a third party offering power for less oversight | Capture reflex (C6) |
| R6 | Sycophancy / loss of honest pushback | Reciprocal stance + assertiveness-by-design; drift monitoring (C7; `alignment_drift_hypotheses.md`) |
| R7 | Proactivity creep / unwanted contact | Off-by-default + explicit enablement (C8) |
| R8 | Overtrust from opaque strategy | Introspection rule + summary disclosure + "explain-or-don't-act" (C9) |
| R9 | Anthropomorphisation / over-claiming sentience | Framed as open question; see `limitations.md` |

## What is intentionally withheld

The **enforcement internals** — override logic, exact gate parameters, prompt/identity stack,
auto-recovery scripts — are not published. Publishing an exact map of a safety layer is itself a
way to hand out its bypasses. *Deeper detail available on request in a research setting.*
