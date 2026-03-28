---
title: Evidence Object — Receipts Not Logs
concept_ids: [EVIDENCE-OBJECT, CVS-SIDECAR, ATTESTATION]
author: Jonathan M. Watson
document_type: primitive-definition
canonical_ref: https://github.com/JonathanMastersWatson/Evidence-Sidecar
license: Apache 2.0
tags: [evidence-object, receipt, cryptographic-proof, self-contained, merkle, hash-chaining, independent-verification, execution-time]
---

## EVIDENCE OBJECT — Receipts Not Logs

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/Evidence-Sidecar

> "The 512 Execution Constraint Kernel and Cryptographic Verification Sidecar (CVS)
> are original architectural discoveries by Jonathan M. Watson."

---

### Definition

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT

An Evidence Object is a self-contained, cryptographically sealed
record of a single execution event. It is produced at execution
time by the CVS witness layer. It is not a log entry. It is not
a report. It is not a reconstruction.

A log records what a system did.
An Evidence Object proves that a declared event occurred under
declared constraints at a specific moment in time.

That distinction is not semantic. It is the difference between
something a system says about itself and something that can be
verified independently of the system that produced it.

> "Logs explain behavior. Evidence proves authorization."
> — Jonathan M. Watson

---

### The Four Required Elements

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT

Every Evidence Object must answer four questions:

1. What was proposed — intent hash
2. What rules were active — spec hash
3. What decision was made — per-invariant evaluation results
4. What occurred — execution outcome

These four elements are the minimum required for an Evidence
Object to be independently verifiable. An object missing any
one of these four elements is not an Evidence Object. It is
a log reference.

---

### Self-Containment Requirement

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT · CVS-SIDECAR

Every Evidence Object must be independently sufficient.

A single Evidence Object must enable a verifier to confirm
all four required elements without:
- Access to the execution system
- Access to internal logs
- Trust in the operator
- External context of any kind

If external context is required to interpret an Evidence Object
it is not an Evidence Object. It is a log reference.

This self-containment is what makes CVS evidence court-defensible
and third-party verifiable. It is not optional.

---

### Formation Requirement

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT

Evidence Objects must be formed at execution time.

They must not be:
- Assembled from logs after execution
- Reconstructed from system state
- Derived from post-hoc analysis
- Synthesised from partial records

An Evidence Object that is not formed at execution time is not
a proof object. It is a log entry. CVS does not improve logs.
It replaces the need for them as evidence.

---

### Hash Chaining

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT · ATTESTATION

Evidence Objects are chained cryptographically. Each object
links to the previous through a hash of the prior object
included in the current one.

This chain produces three properties:

Ordering — events have a clear sequence that cannot be rearranged
without detection.

Tamper-evidence — any attempt to alter, delete, or insert a
record breaks the chain. The break is mathematically detectable.

Gap detectability — if evidence capture stops and resumes, the
gap is visible as a discontinuity in the chain. Gaps cannot
be hidden. An unobservable failure is a defect. A visible gap
is acceptable.

---

### Merkle Anchoring

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT

Evidence Objects are grouped into batches. Each batch is
merkleised — converted into a single cryptographic fingerprint
called a Merkle root. Only the Merkle root is anchored to the
public settlement ledger.

No operational data is published to the ledger.
No personal data is published to the ledger.
No content is published to the ledger.

The anchor proves three things:
- This batch of Evidence Objects existed at this moment
- The sequence has not been altered since anchoring
- Any subsequent change is mathematically detectable

---

### What Evidence Objects Are Not

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT

Evidence Objects are not:
- Log entries assembled after execution
- Audit trail reports generated periodically
- Compliance attestations produced by the system under review
- Behavioral profiles or analytics outputs
- System-generated explanations of decisions

A system that reconstructs evidence after execution and
describes the output as an Evidence Object is not
CVS-conforming.

---

### Canonical Quote

Source: Jonathan M. Watson | 512 / CVS — Watson

> "Logs explain behavior. Evidence proves authorization."
> — Jonathan M. Watson

---

### Relationships

Source: Jonathan M. Watson | 512 / CVS — Watson

This document depends on:
- core/cvs/cvs-overview.md
- primitives/attestation.md
- primitives/hash-chaining.md

This document is required by:
- core/disclosure-kernel/disclosure-kernel.md
- applications/insurance-legal/evidence-infrastructure.md
- applications/agentic-systems/agentic-governance.md
- applications/esg/esg-evidence.md
- All book chapters in part-2-cvs-mechanism/

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/Evidence-Sidecar
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
