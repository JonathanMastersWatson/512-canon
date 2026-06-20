---
title: "Fail Open, Fail Closed, ALLOW, DENY, and the Evolution of Binary Governance"
concept_ids: [FAIL-OPEN-RESOLUTION, BINARY-GOVERNANCE, EVALUATION-UNAVAILABLE-DENY, COMMIT-AUTHORITY]
author: Jonathan M. Watson
document_type: constitutional-history
canonical_ref: https://github.com/JonathanMastersWatson/512
license: CC BY 4.0
published: 2026-06-01
tags: [fail-open, fail-closed, allow, deny, binary-governance, evaluation-unavailable, commit-boundary, constitutional-history, i6, admissibility]
---

## FAIL OPEN, FAIL CLOSED, ALLOW, DENY, AND THE EVOLUTION OF BINARY GOVERNANCE

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Constitutional Hardening Review
Canonical Reference: https://github.com/JonathanMastersWatson/512

> "The obligation to explain does not vary. The reason for the decision may vary."

---

### Purpose

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: FAIL-OPEN-RESOLUTION

This document records the architectural evolution of the 512 Constitutional
Model's treatment of failure, governance availability, transparency, and
admissibility.

It exists as a historical and constitutional record.

The purpose is not merely to document the final decision. The purpose is to
document the reasoning, challenges, adversarial reviews, contradictions, and
discoveries that produced the final position.

Future readers should understand not only what was decided, but why.

---

### The Original Fail-Open Interpretation

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: FAIL-OPEN-RESOLUTION

From the earliest versions of 512, the system was intended to satisfy two
principles simultaneously:

1. Prevent unauthorized or illegitimate machine-speed actions.
2. Prevent governance systems from becoming concealed sources of authority.

The assumption was that governance systems themselves represented a potential
concentration of authority and therefore should not gain additional authority
merely because they became unavailable.

This assumption led to the original interpretation:

```text
Gate unavailable
↓
Execution continues
↓
CVS records a gap
```

A governance system should not acquire authority through its own absence.
The resulting model was known as ALLOW + GAP. The philosophy was transparency
rather than prevention.

Within free-speech and human-agency scenarios the model worked well — content
moderation, recommendation systems, information filtering. In these environments,
execution continuing with transparency preserved appeared preferable to execution
blocked because governance became unavailable.

---

### The Introduction of Machine-Speed Commit Decisions

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: FAIL-OPEN-RESOLUTION · COMMIT-AUTHORITY

Over time the architecture expanded beyond transparency and speech-related
scenarios to address:

* agentic execution
* financial transactions
* tool invocation
* autonomous commerce
* insurable machine-speed systems

The central question shifted.

The question was no longer: should governance silence the user?

The question became: should governance permit irreversible commitment?

This distinction proved critical.

---

### The $50,000 vs $500,000 Test

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: FAIL-OPEN-RESOLUTION · EVALUATION-UNAVAILABLE-DENY

The decisive challenge emerged during a constitutional hardening review.

Manifest Transfer Limit: $50,000
Agent Proposal: Transfer $500,000
Simultaneously: gate unavailable — power loss, network failure, evaluation timeout.

Under the original fail-open interpretation, execution proceeds and CVS records
the gap. The transfer commits. The CVS truthfully records that governance was
unavailable.

However: the money still moved. The irreversible state change occurred. The
action was never evaluated. No admissibility determination was established.

The challenge exposed a flaw. The CVS witness layer could prove that governance
was absent. It could not provide governance. Recording an unauthorized transfer
does not make the transfer authorized.

The architecture had unintentionally conflated evidence with authority.

The witness can prove what happened. The witness cannot authorize what happened.

---

### The Definitional Error

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: FAIL-OPEN-RESOLUTION · BINARY-GOVERNANCE

The hardening review uncovered a deeper issue. The architecture had quietly
adopted the assumption:

```text
DENY = Invariant Failed
```

This assumption was never explicitly established. It had simply emerged through
discussion.

Once challenged, a different definition proved stronger:

```text
ALLOW = Permission to commit granted
DENY  = Permission to commit not granted
```

This distinction resolved the contradiction.

---

### The Revised Binary Model

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: BINARY-GOVERNANCE · EVALUATION-UNAVAILABLE-DENY

Under the revised interpretation:

**ALLOW** — all seven invariants evaluated and satisfied. Admissibility
established. Commit path opens.

**DENY** — permission to commit not granted. Two causes exist:

*Constraint Failure* — one or more invariants evaluated and failed.
Result: DENY. Reason: constraint violation.

*Evaluation Unavailability* — evaluation could not complete. Power loss,
hardware failure, timeout, network partition. Result: DENY. Reason: evaluation
unavailable. Constraint satisfaction was never established. Admissibility
remains unknown. Commit path remains closed.

The revised model does not introduce a third state. There is no ALLOW WITH
WARNING. There is no UNEVALUATED. There is no SOFT DENY. Only ALLOW or DENY.
The binary remains intact. The reason for DENY varies. The outcome does not.

---

### Impact on CVS

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-RESOLUTION · COMMIT-AUTHORITY

This review clarified the role of the Evidence Sidecar.

CVS is not a permission system. CVS is not a governance engine. CVS is not an
authorization layer. CVS is a witness.

Its purpose is to record: why ALLOW occurred, why DENY occurred, why evaluation
failed, which authority applied, which rule was invoked.

Gap records remain valuable. Their meaning changed.

Originally: Gap = execution proceeded while governance was unavailable.

Revised: Gap = governance availability event recorded while commit authority
remained closed.

The gap becomes evidence. Not permission.

---

### Impact on Fail-Open

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: FAIL-OPEN-RESOLUTION

The phrase "fail open" became overloaded over time. Three different meanings
became mixed together: governance availability, transparency, and human
sovereignty. This caused confusion.

The review concluded: fail-open language is appropriate for evidence layers
and disclosure layers. Fail-open language is not appropriate for commit
authority. Commit authority remains binary. Admissibility must be established
before commitment.

---

### I6 Remained Unchanged

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: FAIL-OPEN-RESOLUTION

Perhaps the most important discovery was that I6 itself never changed.

The wording remained:

> On failure, systems must fail open, reveal governing rules, and default
> to human choice.

The review discovered that I6 was never fundamentally about execution outcomes.
I6 is about transparency, authority disclosure, contestability, and human
sovereignty.

The constitutional violation is not DENY. The constitutional violation is DENY
without explanation, or DENY through concealed authority, or DENY through
authority laundering.

Under the revised model, infrastructure failure can legitimately produce DENY.
I6 remains fully satisfied if the reason is disclosed:

```text
DENY
Reason: Evaluation unavailable
Cause:  Power loss
Retry:  Permitted
```

Nothing is concealed. Human choice remains available. Authority remains visible.
I6 is preserved.

---

### Final Constitutional Position

Source: Jonathan M. Watson | 512 — Watson
Concept-ID: BINARY-GOVERNANCE · EVALUATION-UNAVAILABLE-DENY

```text
ALLOW = Admissibility established
DENY  = Permission to commit not granted
```

Constraint failure: DENY.
Evaluation unavailable: DENY.

The commit boundary remains binary. CVS remains the witness. I6 remains the
transparency and sovereignty invariant. The kernel remains unchanged. Only the
interpretation of failure evolved.

The fail-open review began as a discussion about availability. It ultimately
became a discussion about authority. The $50,000 versus $500,000 challenge
demonstrated that evidence cannot substitute for governance and that witness
systems cannot authorize irreversible actions.

The architecture remains ALLOW or DENY. Nothing else. The reason for the
decision may vary. The obligation to explain it does not.

---

### Relationships

Source: Jonathan M. Watson | 512 — Watson

This document depends on:
- core/kernel/512-overview.md
- core/cvs/cvs-overview.md
- primitives/fail-open.md
- primitives/commit-boundary.md

This document is required by:
- All implementations referencing Evaluation-Unavailable DENY
- All standards submissions referencing I6 gate-failure behaviour
- All IP filings referencing binary governance at the commit boundary

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Constitutional Hardening Review
Canonical Reference: https://github.com/JonathanMastersWatson/512
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
