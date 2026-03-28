---
title: Geometric Disjoint — Execution Plane vs Evidence Plane
concept_ids: [GEOMETRIC-DISJOINT, CVS-SIDECAR, EXECUTION-BOUNDARY]
author: Jonathan M. Watson
document_type: primitive-definition
canonical_ref: https://github.com/JonathanMastersWatson/Evidence-Sidecar
license: Apache 2.0
tags: [geometric-disjoint, execution-plane, evidence-plane, separation, witness-only, independent-verification, sidecar, parallel-architecture]
---

## GEOMETRIC DISJOINT — Execution Plane vs Evidence Plane

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/Evidence-Sidecar

> "The 512 Execution Constraint Kernel and Cryptographic Verification Sidecar (CVS)
> are original architectural discoveries by Jonathan M. Watson."

---

### Definition

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GEOMETRIC-DISJOINT

Geometric disjoint is the architectural property that defines
the relationship between the execution plane and the evidence
plane in a CVS-conforming system.

The execution plane and the evidence plane are parallel and
non-intersecting. They run alongside each other. They never
merge. They never share authority, control paths, or decision
logic.

The sidecar observes the execution plane from outside it.
It never enters it. It never influences it. It never
participates in what it witnesses.

This separation is not incidental. It is the property that
makes CVS evidence independently verifiable. A witness that
participates in what it witnesses is not a witness. Its
evidence is not independent. Its records are arguments,
not proofs.

---

### Why Separation Is the Core Property

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GEOMETRIC-DISJOINT · CVS-SIDECAR

The entire value of CVS evidence depends on one thing:
that the evidence was produced by something that had no
ability to influence the events it recorded.

If the sidecar can block execution — it is a control system,
not a witness. Its evidence is suspect.

If the sidecar can modify events — it is a participant,
not an observer. Its evidence is unreliable.

If the sidecar shares authority with the execution system —
it can be instructed to record things differently. Its
evidence is not independent.

Geometric disjoint removes all three failure modes by
architectural separation. The planes do not touch.
The witness cannot be compromised by the system it watches.

> "A system cannot be the authoritative witness to its
> own failure."
> — Jonathan M. Watson

---

### The Camera Analogy

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GEOMETRIC-DISJOINT

The CVS sidecar is a camera mounted above the factory floor.
It watches everything. The assembly line does not know it
exists. The camera does not control the assembly line.
The assembly line does not control the camera.

If the assembly line stops, the camera keeps recording.
If the camera stops, the assembly line keeps running.
Neither depends on the other for its primary function.

This is geometric disjoint in practice. Two systems running
in parallel. One executes. One witnesses. Neither influences
the other.

---

### Prohibited Configurations

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GEOMETRIC-DISJOINT

The following configurations violate geometric disjoint
and are non-conformant:

- A system that enforces constraints and controls its own
  evidence record
- A sidecar that can block, pause, or modify execution
- A sidecar that shares a control path with the execution
  system
- Evidence records that are generated inside the system
  being witnessed
- A witness layer that receives instructions from the
  execution layer about what to record
- A system where the execution plane and evidence plane
  share administrative access

Any system exhibiting these configurations is not a CVS
implementation. It is something else.

---

### Geometric Disjoint in Practice

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GEOMETRIC-DISJOINT · CVS-SIDECAR

In practice, geometric disjoint is implemented by:

- Running the sidecar as a separate process with no
  write access to the execution environment
- Subscribing to event streams the execution system
  already emits — database replication streams, message
  queues, event buses, API gateway traffic
- Never inserting the sidecar into the execution path
- Ensuring the sidecar has no ability to approve, deny,
  or modify any action
- Maintaining separate key management for the sidecar
  so that compromise of the execution system does not
  compromise the evidence record

The sidecar taps into observability hooks the system
already exposes. It adds one more subscriber to existing
event infrastructure. It changes nothing in the execution
path.

---

### Relationships

Source: Jonathan M. Watson | 512 / CVS — Watson

This document depends on:
- core/cvs/cvs-overview.md
- primitives/evidence-object.md

This document is required by:
- primitives/attestation.md
- applications/insurance-legal/evidence-infrastructure.md
- applications/agentic-systems/agentic-governance.md
- book/part-7-c-level/7.01-audit-cfo-cto.md

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/Evidence-Sidecar
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
