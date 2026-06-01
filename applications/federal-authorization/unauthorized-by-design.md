---
title: Unauthorized by Design — Why Federal AI Authorization Fails at the Point of Execution
concept_ids: [CVS-SIDECAR, EVIDENCE-OBJECT, EXECUTION-BOUNDARY, COMMIT-GATE, TEMPORAL-INVERSION, FAIL-OPEN-POSTURE]
author: Jonathan M. Watson
contributor: Mark Gomez (AGICOMPLY)
document_type: white-paper
canonical_ref: https://github.com/JonathanMastersWatson/Evidence-Sidecar
license: CC BY 4.0
published: 2026-05-01
tags: [federal, ato, fedramp, fisma, nist-ai-rmf, omb-m-25-21, govcon, authorization, execution-boundary, commit-gate, cvs, audit, procurement, agicomply, white-paper]
---

## UNAUTHORIZED BY DESIGN — WHY FEDERAL AI AUTHORIZATION FAILS AT THE POINT OF EXECUTION

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/Evidence-Sidecar

> "The 512 Execution Constraint Kernel and Cryptographic Verification Sidecar (CVS)
> are original architectural discoveries by Jonathan M. Watson."

Published: May 2026
Authors: Jonathan M. Watson | 512 / CVS Architecture · Constraint Architect
         Mark Gomez | AGICOMPLY · Founder & CEO · Federal AI Compliance & Authorization
Audience: Federal agency CIOs, procurement officers, GovCon primes, and risk and
authorization leads evaluating AI system posture under current and emerging federal
AI policy.

---

### Abstract

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · EVIDENCE-OBJECT · EXECUTION-BOUNDARY

This paper identifies a structural gap in federal AI authorization practice: systems
are certified before deployment but produce no independent evidence of execution.
It describes the minimal architectural shift required to move proof from
documentation to the moment of action — and the procurement layer that makes that
proof operationally actionable.

The authorization problem exists now, before autonomy arrives. Federal AI governance
conversations are dominated by a future framing — autonomous agents, machine-speed
execution, decision velocity that outpaces any human review cycle. That framing
obscures a failure that is already operating, in production, at human speed.

AI-assisted federal procurement, adjudication, and benefits systems run deliberately.
Analysts review outputs. Supervisors authorize overrides. Program offices produce
audit trails. The process is staffed, governed, and subject to a framework of
authorization controls refined over decades. And yet, the evidentiary record
produced by those processes is structurally insufficient to satisfy the requirements
those frameworks mandate — not because the systems are too fast for oversight, but
because authorization practice certifies systems before deployment and has no
mechanism to verify execution after it.

The gap between what is declared in an Authorization to Operate and what occurs at
the execution boundary is not a compliance gap. It is an architectural one. When
autonomous systems arrive and decision velocity increases by four orders of magnitude,
this gap does not become a new problem. It becomes an irrecoverable one.

The time to address the evidence architecture is now, while federal systems still
operate at a speed that allows the gap to be examined.

```
Current authorization model — certification precedes execution, evidence does not follow it

System Design → Control Mapping → Assessment → ATO Granted → Deployment → Execution → Post-hoc Audit
                                                                                              ↑
                                                                         Evidence reconstructed here
```

---

### The Five Structural Gaps

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT · EXECUTION-BOUNDARY

#### Gap 1 — Authorization Certifies Configuration, Not Execution

The ATO documents the system as assessed. It says nothing about the system as
executing. The gap between them is where decisions are made — and where the record
ends.

The Authorization to Operate is the federal government's primary mechanism for
confirming that an AI system meets the security and control requirements necessary
for operation. The record is accurate at the moment of assessment.

Execution begins after the ATO is granted. Models drift. Data distributions shift.
Control implementations that passed assessment degrade in operation. None of these
changes require a new ATO unless they breach defined significant-change thresholds —
thresholds defined by the system operator and documented in the same plan the ATO
certified.

The ATO record contains what the system declared it would do. The execution record,
where it exists, contains what the system produced. The gap between declaration and
execution — where drift occurs, where judgment is exercised, where admissibility
assumptions break down — is not recorded anywhere.

**At the execution boundary:** the constraint set evaluated at each action is derived
from the canonical specification committed at authorization time. Every execution
event produces an Evidence Object recording which specification version was in force,
whether drift conditions were present, and the binary outcome. The ATO is no longer
a snapshot of assessed configuration. It is a continuously verifiable commitment
against which every execution event is independently evaluated and recorded.

---

#### Gap 2 — Meaningful Human Oversight Is Documented in Controls, Absent from the Execution Record

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT · TEMPORAL-INVERSION

OMB Memorandum M-25-21 requires meaningful human oversight for high-impact AI
decisions. The record shows an analyst approved the output. It does not show whether
that approval was substantive.

In production federal AI environments, human oversight takes a recognizable form.
An analyst is assigned to review AI-flagged cases. The analyst reviews, reaches a
judgment, and approves or rejects. The system log shows: AI flagged, analyst
approved, timestamp recorded. The control is satisfied.

What is absent from the record is the substance of the oversight: what information
the analyst examined, what gave them confidence that the AI output was accurate,
what reasoning they applied to convert machine uncertainty into a human decision.
If that decision is later contested — in litigation, OIG review, or congressional
inquiry — the agency demonstrates that oversight was procedurally present. It cannot
demonstrate that it was substantively exercised.

**At the execution boundary:** human review resolution is a gate-bound event. The
analyst's structured reasoning record — what was examined, what the basis of the
decision was, which uncertainty factors were resolved — is a required input before
the approval commits. Without it, the approval does not execute. Meaningful oversight
is no longer an assertion about process. It is a condition of execution.

---

#### Gap 3 — Continuous Monitoring Records Telemetry, Not Decisions

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · EVIDENCE-OBJECT

FedRAMP continuous monitoring tracks configuration drift and vulnerability exposure.
It does not record whether a specific AI decision was made within declared authority,
against a currently valid model, by an actor whose authorization covered that action.

Continuous monitoring under FedRAMP and FISMA captures the operational condition of
a system over time: patch levels, configuration state, vulnerability findings, access
log anomalies. When an AI system produces a consequential output, the continuous
monitoring record confirms the system was running and in its authorized configuration.
It does not confirm that the specific decision was made within the declared scope of
the system's authorized behavior, by an actor whose delegated authority covered that
specific action category, against an AI model whose calibration had been validated
within the required timeframe.

Those are not telemetry questions. They are decision-level evidence questions.
Correlation is not evidence. It is inference, and inference under adversarial
scrutiny does not hold.

**At the execution boundary:** every decision event produces a cryptographically
signed Evidence Object — a structured record of what was proposed, which constraints
were evaluated, what delegated authority was in force, the model calibration state,
and the binary outcome — generated at execution time, hash-chained to its
predecessors, and anchored to a public ledger every 30 to 60 seconds. Continuous
monitoring remains the system health layer. Decision evidence is a structurally
separate, independently verifiable record that requires no correlation, no
reconstruction, and no operator cooperation to be read.

---

#### Gap 4 — Degraded Operation Is Classified in the CONOPS, Invisible in the Evidence Chain

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: FAIL-OPEN-POSTURE · CVS-SIDECAR

Federal systems operate under Continuity of Operations Plans that define authorized
fallback procedures when primary AI systems are unavailable. The plan is sound. The
execution of the plan — which decisions were affected, over what period, against what
standard — leaves no trace in the evidence record beyond the classification of a
processing pathway.

Knowing that a decision was made in manual fallback mode is not the same as knowing
whether the manual process was accurate, authorized, and within the declared scope
of the fallback procedure. A regulatory examiner or OIG reviewing a contested
decision determines that the system was in degraded operation. It cannot determine
whether the decision made during that degraded operation met any specific standard
of correctness, authority, or process compliance.

**At the execution boundary:** degraded operation produces an explicit first-class
record in the evidence chain — state classification, timestamp, which gate conditions
were unavailable, and the boundaries of ungoverned execution. Gaps in the evidence
chain are recorded with the same cryptographic integrity as governed events. An
agency demonstrates precisely what was governed and what was not, over what period,
and under what fallback conditions. Ungoverned operation is no longer absorbed
quietly into the audit record. It is observable, bounded, and measurable.

---

#### Gap 5 — Control Mappings Are Assertions — No Mechanism Verifies Them at Runtime

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EXECUTION-BOUNDARY

A system's authorization package maps its capabilities to NIST SP 800-53 controls.
That mapping is a document. No mechanism in current authorization practice verifies,
at the moment of execution, that the declared control is in force and functioning.

Control implementations that satisfied assessment degrade in operation without
triggering a significant-change threshold. A logging control that passed assessment
becomes inconsistently applied as system updates accumulate. An access control
mapped to AC-3 is technically present but operationally bypassed through a fallback
code path no assessment examined. A model governance control was valid at assessment
time and invalid six months later when the underlying model was retrained without a
corresponding authorization event.

The mapping says the control is present. Nothing confirms whether it was present —
and functioning — at the moment a specific decision executed.

**At the execution boundary:** the constraint set evaluated at each action includes
a current-state attestation for each applicable control: access authority scope,
model calibration status, logging integrity state, and declared operational mode.
The gate evaluates whether the control is in force at this execution moment — not
whether it was in force at assessment time. A control that has degraded produces a
denial and a recorded gap, not a silent pass. The assessment record documents the
declared environment. The execution record documents the actual one.

---

### Fraud Does Not Occur After Execution — It Commits at the Boundary

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: COMMIT-GATE · EVIDENCE-OBJECT

Current federal AI systems detect fraud after execution. Evidence is reconstructed
after the fact, authority violations are identified through audit sampling, and
anomalies surface in review cycles that run weeks or months behind the decisions
they examine. By the time fraud is detected, it has committed.

Under this architecture, fraud does not move to detection. It moves to prevention.

An unauthorized action — a contract approval that exceeds delegated authority, a
procurement decision that bypasses required validation, an AI-driven adjudication
that applies a model outside its certified scope — cannot commit without satisfying
every declared constraint at the boundary.

There is no interpretation step. There is no post-hoc review window. There is no
administrative reconciliation path. The action either satisfies the constraint set
at execution — in which case it commits with a complete, independently verifiable
record — or it does not satisfy the constraint set, in which case it does not exist
as an operational event. The denial is recorded. The state does not change.

Fraud is not detected after execution. Fraud is structurally prevented from
committing without valid authority, valid constraint satisfaction, and a verifiable
execution record.

---

### Regulatory Frameworks Require What Current Authorization Practice Cannot Produce

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT

Every major federal AI governance framework now mandates proof of execution — not
documentation of intent. Current authorization practice produces the latter.

The NIST AI Risk Management Framework (AI RMF 1.0) treats the inability to
reconstruct decisions under audit conditions as a governance posture failure
regardless of measured system accuracy. OMB Memorandum M-25-21 mandates that
agencies deploying high-impact AI maintain mechanisms capable of demonstrating that
human oversight was not only procedurally present but substantively exercised.
Executive Order 14110 and its successors require auditable records of AI system
behavior in security and safety-critical applications.

FedRAMP's continuous authorization model moves toward ongoing verification rather
than point-in-time assessment — but its monitoring infrastructure captures system
health telemetry, not decision-level evidence. The framework recognizes the need for
continuous verification. The evidence layer required to satisfy it does not exist in
standard federal AI deployments.

Each framework assumes the decision record was created at execution time. Each of
the five structural gaps documented above demonstrates that it was not — not through
negligence, but because the architecture places the recording boundary after the
decision boundary. Closer monitoring, more frequent assessments, and richer system
logs do not close this gap. They produce more detailed records of the same structural
absence.

---

### Compliance Platforms Cannot Independently Verify Themselves

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR

A compliance platform monitors the AI system it is deployed alongside. Its logs,
dashboards, and audit exports are produced by the same operational environment they
are documenting. Under federal regulatory examination, an Inspector General review,
or GAO audit, that evidence carries the weakest possible evidentiary standing: it is
assertion by the interested party.

This is not a criticism of compliance platforms. It is a structural property of any
evidentiary system that is part of the environment it observes. Providing independent
evidence of system behavior requires a component that is architecturally separate
from every system it observes — not integrated, not co-deployed in the same stack,
not relying on the same infrastructure.

---

### 512 and CVS Are Not AI — That Is Precisely the Point

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: COMMIT-GATE · CVS-SIDECAR

Every AI compliance platform in the federal market has a confidence problem. 512 and
CVS do not.

AI systems are probabilistic. They optimize for statistical outcomes, express
confidence without guaranteed accuracy, and drift as their operating environments
diverge from their training data. Governing AI with AI compounds the problem — the
governance layer inherits the same failure modes it is supposed to detect.

512 and CVS are not AI. They are deterministic constraint infrastructure — the layer
that operates below AI systems and beside governance platforms, enforcing what those
platforms declare and producing proof that is independent of everyone in the room.

A Commit Gate is positioned at the execution boundary — the precise point at which a
proposed action becomes an irreversible state change. It carries an immutable
constraint set. It evaluates each proposed action against that set simultaneously
across every applicable invariant and produces one of two outputs: allow or deny.
It does not learn, drift, weight, or interpret. It enforces declared policy before
execution proceeds, at speeds between 10 and 50 microseconds.

CVS — the Cryptographic Verification Sidecar — is the independent witness layer. It
operates in parallel with any execution surface without touching the execution path.
Every observed event produces an Evidence Object: a structured, cryptographically
signed record, hash-chained to its predecessor, anchored to a public ledger every 30
to 60 seconds at approximately $1.08 per month. Retroactive alteration of any
Evidence Object breaks every subsequent link in the chain — detectable through
independent verification without operator cooperation.

The architecture is agnostic to upstream governance platforms and downstream
compliance systems. Whatever federal compliance platform an agency selects, it still
requires independent proof that the platform operated as declared. No vendor provides
that proof about their own system. 512 and CVS provide it about any system.

---

### Execution at the Commit Boundary

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: COMMIT-GATE · EVIDENCE-OBJECT · TEMPORAL-INVERSION

Evidence is not reconstructed after the fact. It is generated at the moment the
decision is made.

```
The commit boundary

Proposed Action → [COMMIT GATE] → Commit
                        |
                       CVS

Before [COMMIT GATE]: proposal. After Commit: irreversible fact.
CVS records what was proposed, what was evaluated, and what was decided.
```

| STAGE | CURRENT FEDERAL SYSTEM | WITH 512 / CVS |
|---|---|---|
| Decision basis | AI output, analyst judgment — implicit | Proposed action evaluated against declared, committed constraints |
| Evaluation method | Interpretive; reconstructed post-hoc if contested | Deterministic, simultaneous, binary — at execution time |
| Record produced | Outcome only; control mappings asserted separately | Full boundary record: inputs, constraint results, authority attestation, outcome |
| Evidence independence | Vendor-internal; operator cooperation required to read | Public ledger anchored; verifiable without operator cooperation |
| ATO relationship | ATO certifies declared configuration | ATO commitment verified against every execution event |

---

### What This Looks Like in Practice — A Federal Contract Action

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: COMMIT-GATE · EVIDENCE-OBJECT

A contracting officer at a federal agency is processing an AI-assisted contract
approval. The AI system has scored the procurement against policy requirements and
returned a recommendation to approve. The contracting officer initiates the approval
action. This is the commit boundary — the moment a proposed action moves toward
irreversible state change.

**CONTRACT APPROVAL — EXECUTION AT THE BOUNDARY**

1. **Intent declared.** Contracting officer initiates approval. System records:
   proposed action type (contract approval), action value ($2.4M), actor identity,
   timestamp, AI confidence score (91%), and source model identifier.

2. **Gate evaluates — authority attestation fails.** The contracting officer's
   delegated purchasing authority is attested to $1M. The proposed action value
   ($2.4M) exceeds the attested scope. The gate returns DENY on the authority
   invariant. No other invariants are evaluated. The action does not commit.

3. **CVS generates Evidence Object.** The denial is recorded: proposed action,
   constraint evaluated, invariant that failed (authority scope), attested limit,
   proposed value, actor, timestamp. The record is cryptographically signed and
   chained. It cannot be altered.

4. **Denial routes upstream.** The system returns a structured signal: action
   blocked — authority scope not sufficient for this contract value. The action
   routes to the authority registry for escalation or re-attestation.

5. **Action re-submitted with valid attestation.** Senior contracting official with
   attested authority above $2.4M initiates the action. Gate evaluates: authority
   attested, model calibration current, reasoning record present, operational state
   valid. All invariants return true. Action commits.

6. **AGICOMPLY maps to procurement framework.** The Evidence Object fields are
   mapped to NIST SP 800-53 AC-3 (access enforcement), AU-10 (non-repudiation), and
   OMB M-25-21 human oversight attestation. A procurement-ready compliance artifact
   is produced for the authorization record.

The first denial is not an error. It is a structured signal: the authority registry
did not have the correct attestation in force before the action was attempted. The
boundary does not create the problem. It exposes it precisely.

---

### Three Operational States

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · COMMIT-GATE · FAIL-OPEN-POSTURE

#### State 1 — Observation Mode: CVS in a Human-Speed Federal System

The system does not change. The workflow does not change. Only what can be proven
changes.

```
Observation Mode — CVS beside the workflow, not in it

Request → AI Analysis → Analyst Review → Authorization → Execution → Record
   |           |              |               |              |          |
  CVS         CVS            CVS             CVS            CVS       CVS

CVS observes state transitions at each stage. Execution is unchanged.
CVS does not intercept, block, or influence any step.
```

CVS runs in parallel with existing federal AI workflows. No system changes are
required. No workflow interruptions occur. The result is something no federal AI
deployment currently has: a real-time map of execution conformance against declared
authorization constraints.

This is reversible. If CVS is removed, the system operates exactly as before. The
evidence record produced during CVS operation remains on the public ledger.

#### State 2 — Pre-Enforcement Evaluation Mode: 512 Without Blocking

Before enforcement begins, the 512 boundary evaluates every proposed action against
declared constraints — and records what would have passed and what would have failed
— without blocking execution.

```
Pre-Enforcement Evaluation Mode

Proposed Action → [512 BOUNDARY — EVALUATING, NOT BLOCKING] → Execution proceeds
                                    |
                           Result: ALLOW / DENY
                                    |
                           CVS records evaluation result
```

The output of this phase is a readiness signal: the precise distribution of allow,
deny, and gap results across the agency's actual transaction volume. Before a single
action is blocked, the agency has a complete, evidence-backed picture of which
constraint definitions are calibrated correctly and what the enforcement failure rate
would be on day one.

#### State 3 — Enforcement Mode: 512 + CVS at Full Deployment

```
Enforcement Mode — human upstream, gate at the boundary, CVS beside it

Policy / Authority Registry / Model Validation / Control Definitions
                         |
                [Declared Constraints]
                         |
Proposed Action → [COMMIT GATE] → Commit → Execution
                        |
                       CVS

Humans operate upstream. No human decision occurs at the boundary.
Gate evaluates constraints. CVS records at evaluation. Binary outcome only.
```

| CAPABILITY | CVS ONLY | 512 + CVS |
|---|---|---|
| Visibility into execution | Yes | Yes |
| Independent evidence | Yes | Yes |
| Prevent unauthorized actions | No | Yes |
| Hidden decisions | Visible | Eliminated |
| Execution speed support | Human-speed | Machine-speed |
| ATO-defensible evidence | Partial | Structural |

---

### Failure Mode Mapping — Gate Conditions and Upstream Responsibility

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: COMMIT-GATE · EVIDENCE-OBJECT

| FAILURE MODE | GAP IN CURRENT ARCHITECTURE | GATE CONDITION (512 / CVS) | UPSTREAM SYSTEM |
|---|---|---|---|
| ATO certifies configuration, not execution | Runtime drift not captured between assessment cycles | Constraint set derived from committed specification; drift conditions produce denial and gap record | Authorization Management / Configuration Control |
| Human oversight undocumented at decision point | Analyst approval recorded; reasoning absent | Without structured reasoning input, the approval does not commit | Agency Review Process / AI Governance |
| Continuous monitoring records telemetry, not decisions | Decision-level evidence requires reconstruction from correlated logs | Evidence Object created at execution time; no reconstruction required | IT Operations / ISSO |
| Degraded operation invisible in evidence chain | Fallback processing classified but not witnessed | Degraded state recorded explicitly; gap bounded and timestamped | COOP / Continuity Planning |
| Control mappings asserted, not runtime-verified | SSP mapping valid at assessment; no mechanism verifies it at execution | Control attestation evaluated at each execution event; failed attestation produces denial | Security Engineering / Authorizing Official |

---

### The Constraint Architect: A New Role and a New Professional Services Category

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: COMMIT-GATE

The primary failure point is not enforcement. It is constraint definition.

512 enforces precisely what it is declared to enforce. Bad constraint definitions
produce perfectly wrong outcomes. This points to a function most federal agencies
and GovCon primes do not yet have a name for: the Constraint Architect — the
practitioner who translates governance intent into machine-enforceable constraint
sets, closing the gap between what policy declares and what the gate enforces.

The Constraint Architect is both a new role and a new professional services category.
The analogy is direct: when organizations undertook major operational transitions —
process reengineering, ERP adoption, post-Sarbanes-Oxley control redesign — they
engaged specialist firms. McKinsey, Deloitte, Accenture, and their equivalents built
practices around those transitions because the transitions were real, the expertise
was scarce, and the cost of encoding the wrong assumptions was structural rather than
correctable after the fact. Constraint architecture is the same category of
engagement: a scoped, deliverable professional services function that produces a
machine-enforceable constraint set the gate runs against.

The gate enforces exactly what it is told. What it is told must be right. That is
not a technology problem. It is a governance design problem — and it has a
professional services answer.

---

### Path to Implementation

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · COMMIT-GATE

**Phase 1 — Observation.** CVS deploys as an independent witness of the existing
federal AI system. No system changes. No workflow interruption. The output is the
first accurate baseline of execution conformance: which decisions route automatically,
which require human review, which involve override authority, where evidence chain
gaps appear.

**Phase 2 — Passive Evaluation.** The 512 boundary deploys in pre-enforcement
evaluation mode. Every proposed action is evaluated against the declared constraint
set. Execution is not blocked. The output is a readiness signal: the distribution of
allow and deny results across actual transaction volume. Constraint definitions are
hardened against real behavior.

**Phase 3 — Selective Enforcement.** The gate activates on the highest-risk
execution surfaces first: delegated authority overrides, AI-flagged exception
approvals, high-value contract actions.

**Phase 4 — Full Enforcement.** The entire execution surface operates inside the
gate boundary. Authorization is no longer a certification that precedes the system.
It is a property that every execution event carries.

The implementation timeline is determined by constraint definition, not by
technology. The technology is available and open.

---

### Contributed Section — AGICOMPLY: From Execution-Bound Proof to Procurement-Ready Compliance

Source: Mark Gomez | AGICOMPLY · Founder & CEO
Concept-ID: CVS-SIDECAR · EVIDENCE-OBJECT

*Contributed by Mark Gomez, Founder & CEO, AGICOMPLY. AGICOMPLY is a federal AI
compliance platform focused on procurement-grade evidence and chain-of-custody
assurance for AI system authorization.*

#### The Structural Gap Between Proof and Procurement

The 512/CVS architecture solves the evidentiary problem at the execution layer. It
produces a proof record that is cryptographically sound, independently verifiable,
and tamper-evident. What it does not do — by design — is translate that proof record
into the language that federal procurement officers, NIST assessors, and ATO
authorities require to act on it.

That translation is the gap AGICOMPLY fills. There is no transformation step. The
Commit Gate produces a fact. The Cryptographic Verification Sidecar witnesses it.
AGICOMPLY performs deterministic mapping of already-formed proof into
procurement-recognized compliance language — the specific NIST SP 800-53 control,
the RMF artifact it satisfies, the OMB M-25-21 requirement it evidences. AGICOMPLY
does not create evidence. It reads proof that already exists on the public ledger
and maps it to the framework language that authorization processes require.

#### AGICOMPLY as the Interpretation Plane

The three-layer architecture — enforcement, witness, interpretation — separates
functions that current systems collapse together. 512 enforces at the commit
boundary. CVS witnesses independently. AGICOMPLY operates as the interpretation
plane: consuming read-only Evidence Objects from the CVS access layer, mapping their
fields to control frameworks, and surfacing the results as procurement-ready
artifacts without touching the execution path or the evidence record.

This separation is load-bearing. If the interpretation layer wrote to the evidence
record, it would compromise the independence of the evidence. AGICOMPLY does not
write to CVS output. It reads, maps, and presents — the same relationship that a
financial auditor holds to an account record.

#### The Six-Step Governance Loop

1. **Intent declared** — Proposed action entered with authority context
2. **Constraint evaluation** — Commit Gate evaluates against declared invariants (binary)
3. **Independent witness** — CVS generates Evidence Object at evaluation moment
4. **Proof Object formed** — Cryptographically signed, hash-chained, ledger-anchored
5. **Control mapping** — AGICOMPLY maps Proof Object fields to NIST/RMF controls
6. **Third-party verification** — Independent Validator confirms proof without system access

#### Mapping to Federal Procurement Frameworks

| FRAMEWORK | SPECIFIC REQUIREMENT | PROOF OBJECT FIELD | AGICOMPLY MAPPING OUTPUT |
|---|---|---|---|
| NIST AI RMF 1.0 | GOVERN 1.1: AI risk policies established and enforced | constraint_spec_hash, invariant_results[] | RMF GOVERN artifact with hash-verified policy reference |
| NIST SP 800-53 | AC-3: Access Enforcement | authority_attestation, actor_scope | AC-3 control evidence record with cryptographic attestation |
| NIST SP 800-53 | AU-10: Non-repudiation | evidence_chain_hash, ledger_anchor_tx | Non-repudiation artifact with public ledger reference |
| OMB M-25-21 | Meaningful human oversight for high-impact AI | reasoning_record_hash, oversight_attestation | Human oversight evidence record with structured reasoning proof |
| FedRAMP | Continuous authorization: runtime control verification | operational_state, control_attestation_timestamp | Continuous monitoring artifact with per-decision control status |

#### The Disclosure Kernel

Federal procurement frequently requires proof of compliance without exposure of the
complete evidence chain. The Disclosure Kernel addresses this through proof
minimization: selective field disclosure, Merkle inclusion proofs, and specification
hash verification that allow a third party to confirm that a specific transaction
satisfied defined constraints — without exposing the full evidence chain or the
internal logic of the executing system.

---

### Authorization Cannot Be Achieved After Execution

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: TEMPORAL-INVERSION · EVIDENCE-OBJECT

The evidence problem exists today, at human speed. It does not wait for autonomous
systems.

The regulatory enforcement trajectory makes the consequence concrete. Agencies that
deploy AI systems without execution-bound evidence face growing exposure under AI
RMF-aligned authorization requirements, OMB M-25-21 implementation guidance, and
the expanding oversight posture of Inspector General and GAO functions developing
AI-specific audit methodologies.

Authorization constructed before execution — enforced at the commit boundary,
witnessed independently by CVS, mapped into procurement-ready compliance artifacts
by AGICOMPLY — is not a stronger version of current authorization practice. It is
a different category, operating at the only moment when the question of what was
authorized still has a determinable answer.

This architecture does not improve authorization. It replaces it at the point where
authorization becomes real.

---

### Regulatory Alignment

Source: Jonathan M. Watson | 512 / CVS — Watson

| FRAMEWORK | CORE REQUIREMENT | GAP IN CURRENT ARCHITECTURE |
|---|---|---|
| NIST AI RMF 1.0 | End-to-end traceability; decision reconstruction under audit | ATO certifies declared configuration; runtime execution produces no independent decision record |
| OMB M-25-21 | Meaningful human oversight for high-impact AI decisions | Analyst approval recorded; reasoning structurally absent at point of highest regulatory exposure |
| FedRAMP Continuous Authorization | Ongoing control verification beyond point-in-time assessment | Continuous monitoring captures telemetry; decision-level evidence requires reconstruction |
| FISMA / NIST SP 800-53 | Unbroken audit trail; non-repudiation; access enforcement | Control mappings asserted at assessment time; no mechanism verifies them at execution |
| EO 14110 (and successors) | Auditable records of AI behavior in safety-critical applications | Degraded mode operation classified but not independently witnessed in evidence chain |

---

### Relationships

Source: Jonathan M. Watson | 512 / CVS — Watson

This document depends on:
- kernel/INVARIANTS.md
- core/cvs/cvs-overview.md
- primitives/evidence-object.md
- primitives/execution-boundary.md
- primitives/attestation.md

This document is related to:
- applications/insurance-legal/uninsurable-by-design.md
- papers/004-settlement-operating-control.md

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/Evidence-Sidecar
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
