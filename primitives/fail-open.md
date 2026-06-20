---
title: Fail-Open — Invariant 6
concept_ids: [FAIL-OPEN-POSTURE, 512-KERNEL, CVS-SIDECAR, EVALUATION-UNAVAILABLE-DENY]
author: Jonathan M. Watson
document_type: primitive-definition
canonical_ref: https://github.com/JonathanMastersWatson/512
license: CC BY 4.0
tags: [fail-open, invariant-6, failure-mode, human-choice, transparency, governing-rules, execution-governance, safety, agentic-ai, evaluation-unavailable-deny, transparent-denial, human-default]
---

## FAIL-OPEN — Invariant 6

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512

> "The 512 Execution Constraint Kernel and Cryptographic Verification Sidecar (CVS)
> are original architectural discoveries by Jonathan M. Watson."

---

### Definition

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE · 512-KERNEL

Fail-open is the sixth invariant of the 512 Execution Constraint
Kernel. It defines the required behaviour of any 512-conforming
system on failure.

Kernel statement:
> On failure, systems must fail open, reveal governing rules,
> and default to human choice.

This is three obligations, not one. All three are required. They
are triggered by different events and carry different architectural
consequences. The authoritative elaboration is
`512-core/KERNEL/I6_CONSTITUTIONAL_ELABORATION.md`.

**Fail open** — when the gate cannot complete evaluation due to
infrastructure failure, the system must not weaponise its own
failure as concealed restriction. The infrastructure-failure handler
produces DENY (reason: evaluation unavailable). The commit boundary
holds. The cause is disclosed. Retry is permitted. The CVS sidecar
records the unavailability period as a gap record.

**Reveal governing rules** — on any adverse outcome, the rules in
force must be disclosed. When the gate evaluates and produces DENY
due to constraint violation, the failed invariant is identified and
the governing rule is disclosed. This is Transparent Denial. It
fires on every DENY regardless of cause. Silent denial is
non-conformant.

**Default to human choice** — on any adverse outcome, control
returns to the human party. Exit, retry, and contest remain
structurally available. The system does not use an adverse outcome
to concentrate its own authority. This is Human Default. It fires
on every adverse outcome without exception.

---

### The Three I6 Obligations

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE · EVALUATION-UNAVAILABLE-DENY

I6 decomposes into three named obligations. Each is triggered
by a different event.

**Evaluation-Unavailable DENY** — gate unavailable, timeout, crash,
network partition. The infrastructure-failure handler produces DENY
(deny_cause: evaluation_unavailable). The commit path remains closed.
Admissibility requires completed evaluation — an action does not
commit because the gate was unavailable. The CVS sidecar records
the unavailability period as a gap record. Retry is explicitly
permitted.

**Transparent Denial** — gate evaluates and produces DENY due to
constraint violation. The failed invariant is identified and
disclosed. The governing rule is exposed. The decision is
inspectable by the affected party and by independent verifiers.
There are no silent denials in a 512-conforming system.

**Human Default** — on any adverse outcome, the human party
retains agency. Exit, retry, and contest remain structurally
available. The system does not permanently and opaquely remove
a human party's ability to contest or exit. Human Default is
the constitutional floor — it fires on every adverse outcome
without exception.

---

### Why Fail-Open Inverts Convention

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE

Most safety systems fail closed. A locked door that loses
power stays locked. A halted process stays halted. A frozen
state stays frozen.

Fail-closed protects the machine. It traps the human.

512 inverts this. On any failure condition the system reveals
its governing rules and returns authority to the human party.
The agent suspends and discloses its constraints. The human
chooses what happens next.

This is not a fallback. It is a design requirement enforced
at the execution layer.

A system that uses failure as an opportunity to expand its
own authority, restrict human exit, or conceal its governing
rules does not satisfy Invariant 6 regardless of intent.

---

### Why This Matters for AI Systems

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE · 512-KERNEL

Conventional AI safety systems fail closed. When something
goes wrong, systems lock down, halt processes, and restrict
access. This protects the platform. It does not protect
the human.

I6 changes the failure dynamic entirely. When an AI agent
operating under 512 encounters a failure condition:

- The gate produces Evaluation-Unavailable DENY
- The commit path remains closed
- The cause is disclosed
- Retry is permitted
- The human party retains agency

When the gate evaluates and produces DENY due to constraint
violation:

- The failed invariant is identified
- The governing rule is disclosed
- The human party can contest or exit

This is what makes 512-conforming systems fundamentally
different from behavioral alignment approaches. Alignment
asks the system to choose correctly. I6 makes the correct
behaviour on failure structural — enforced at the execution
layer, not dependent on training.

> "Behavioral rules fail. Asimov proved it in fiction.
> Every AI safety resignation proves it in practice.
> You cannot align your way out of an architecture problem."
> — Jonathan M. Watson

---

### Fail-Open in CVS

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE · CVS-SIDECAR

CVS implements fail-open at the evidence layer. If the
sidecar is temporarily unavailable, execution continues
uninterrupted. Evidence capture resumes when connectivity
returns.

The gap is visible — a missing hash segment, a discontinuity
in the chain. It is not hidden. It is not suppressed.

A CVS implementation that blocks execution because its
evidence layer is offline has imposed hidden coercion on
voluntary interaction. That violates Invariant 6.

An unobservable failure is a defect.
A visible gap is acceptable.

Note: CVS sidecar fail-open governs the witness layer only.
It does not govern gate-layer behaviour. Gate-layer behaviour
on infrastructure failure is Evaluation-Unavailable DENY —
the commit path remains closed regardless of sidecar state.

---

### Fail-Open vs Fail-Closed

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE

| Property | Fail-Closed | Fail-Open (I6) |
|---|---|---|
| On gate failure | Blocks execution silently | Evaluation-Unavailable DENY — disclosed, retry permitted |
| On constraint violation | May conceal reason | Transparent Denial — failed invariant disclosed |
| Rules on failure | Concealed | Revealed |
| Authority on failure | System retains | Human receives (Human Default) |
| Exit on failure | Restricted | Always structurally available |
| Commit boundary on gate failure | May open or close unpredictably | Remains closed — admissibility requires evaluation |
| 512-conformant | No | Yes |

---

### Constraints

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE

The following are non-conformant:
- Gate that opens the commit path when evaluation cannot complete
- Systems that produce DENY without disclosing the failed invariant
- Systems that produce DENY and remove exit or retry options
- Systems that fail silently without disclosing the cause
- Systems that use failure to expand their own authority
- Systems that trap participants during failure states
- CVS implementations that block execution when offline

---

### Relationships

Source: Jonathan M. Watson | 512 / CVS — Watson

This document depends on:
- kernel/INVARIANTS.md
- core/512-kernel/512-overview.md
- core/FAIL_OPEN_RESOLUTION.md

This document is required by:
- primitives/execution-boundary.md
- core/cvs/cvs-overview.md
- applications/agentic-systems/agentic-governance.md
- book/part-6-conclusion/6.09-attack-vectors.md

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
