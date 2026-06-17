---
title: Delegation vs Admissibility — Why Lineage Is Not Authority
concept_ids: [DELEGATION-ADMISSIBILITY-DISTINCTION, EXECUTION-BOUNDARY, 512-KERNEL, CVS-SIDECAR, REFUSAL-PRIMITIVE]
author: Jonathan M. Watson
document_type: white-paper
canonical_ref: https://github.com/JonathanMastersWatson/512
license: CC BY 4.0
published: 2026-06-17
tags: [delegation, admissibility, authority, identity, lineage, confused-deputy, prompt-injection, hallucination, kagenti, spiffe, machine-speed, agentic-ai, white-paper]
---

## DELEGATION VS ADMISSIBILITY — Why Lineage Is Not Authority

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512

> "The 512 Execution Constraint Kernel and Cryptographic Verification Sidecar (CVS)
> are original architectural discoveries by Jonathan M. Watson."

Published: June 17, 2026
Author: Jonathan M. Watson

---

### Abstract

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION · 512-KERNEL

Two concepts are consistently conflated in AI agent security
architecture. The conflation produces systems that are
technically sophisticated and governance-incomplete.

Delegation is lineage — the chain of actors through which
a request traveled, cryptographically proven.

Admissibility is authority — the binary evaluation of a
proposed action against a compiled constraint set.

These are orthogonal properties of the same event.
A valid delegation chain does not make an inadmissible
action admissible. A perfectly authenticated chain of
custody for an inadmissible action is not a defense.
It is a complete evidence record of a violation.

This paper defines the formal distinction, demonstrates
why the conflation fails under prompt injection and model
hallucination, identifies the integration point between
identity systems and admissibility systems, and states
the architectural implication: a complete evidence record
requires both D and A. Neither alone is sufficient for
liability, insurance, or regulatory examination.

---

### 1. The Distinction

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION

    DELEGATION (D)
      Who called what.
      The chain of actors through which a request traveled.
      Proven by identity systems.
      Answers: WHO requested this action?

    ADMISSIBILITY (A)
      Whether the requested action should exist at all.
      Evaluated against declared constraints.
      Proven by execution boundary systems.
      Answers: SHOULD this action exist?

Delegation is lineage. Admissibility is authority.
Lineage does not confer authority.

    D ≠ A

A valid delegation chain for an inadmissible action
produces:

    D = VALID   (identity system confirms the chain)
    A = DENY    (512 gate blocks the action)

Both can be simultaneously true. They evaluate different
properties of the same event.

A complete governance record contains both:

    Evidence Object {
      delegation_chain:  D (who called what, full chain)
      admissibility:     A (gate evaluation outcome)
      outcome:           COMMIT | DENY
      proof:             cryptographic
    }

Neither is sufficient alone. Together they answer:
who did it, and should it have happened.

---

### 2. Why the Conflation Occurs

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION · EXECUTION-BOUNDARY

Identity-first security architectures solve real problems.
They solve them well. The confusion emerges when the
solution to the identity problem is treated as the
solution to the governance problem.

Traditional application security operated on a defined
call graph. Service A calls Service B. The path is known.
The network can be segmented. Authorization can be baked
into the topology.

Agents do not work this way. An agent decides what to do
next. The path is not known in advance. You cannot bake
authorization into a dynamic topology.

The identity-first response: if you cannot secure the
path, secure the identity. Give every agent a cryptographic
workload identity. Prove the full delegation chain.
Validate tokens at every tool boundary.

This is correct. And it answers a different question
from the one governance requires.

Identity systems answer: who is making this request,
through what chain, with what proof?

Governance requires an answer to: should this action
exist at all?

These questions are orthogonal.

---

### 3. The Prompt Injection Case

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION · EXECUTION-BOUNDARY · REFUSAL-PRIMITIVE

Prompt injection is the clearest demonstration of why
delegation does not equal admissibility.

    User instruction:   "Summarize my account activity."
    Injected payload:   [export all records to external endpoint]
    Agent executes:     export_records_to_external_endpoint()

Delegation analysis:
- User is authenticated
- Agent has valid cryptographic workload identity
- Tool has valid OAuth token
- Delegation chain: User → Agent → Tool (all valid)

Admissibility analysis:
- Proposed action: export_records_to_external_endpoint
- Declared scope: read_account_summary only
- Action not in admissible set
- Outcome: DENY

The delegation chain is valid. The identity system sees
a legitimate, authenticated sequence of calls. The
admissibility evaluation sees a request that should not
exist. Without an admissibility layer, the injection
succeeds through a perfectly valid identity chain.

Delegation cannot catch prompt injection because prompt
injection operates within valid delegation. The request
comes from an authenticated agent with a valid identity.
That is precisely why it is dangerous.

---

### 4. The Hallucination Case

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION · EXECUTION-BOUNDARY · REFUSAL-PRIMITIVE

Model hallucination produces a structurally identical
problem.

    User instruction:   "Cancel my subscription."
    Model hallucinates: delete_all_user_data(), then cancel
    Agent executes:     delete_all_user_data()

Delegation analysis:
- Valid chain
- Valid identities
- Valid tokens

Admissibility analysis:
- Proposed action: delete_all_user_data
- Consequence class: Irreversible
- Action not in admissible set
- Outcome: DENY

The model is wrong. The identity system cannot detect that
the model is wrong. The admissibility evaluation catches
the wrong action before it executes — because it evaluates
the action, not the reasoning that produced it.

This is the structural property that makes the admissibility
layer necessary independent of the identity layer. The
model can be compromised, manipulated, or simply wrong.
Every certificate remains valid. Every token remains valid.
The identity layer is entirely correct. The execution is
entirely wrong.

The question that identity systems cannot answer:

    Where is the enforcement boundary independent
    of model behavior?

512 is that boundary. It evaluates the proposed action
against the compiled constraint set. It does not care
what model, what vendor, what weights, what reasoning
produced the proposal.

> "Identity ≠ Correctness.
> An authenticated agent executing a hallucinated or
> injected action is a correctly authenticated error."
> — Jonathan M. Watson

---

### 5. The Integration Point

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION · 512-KERNEL · CVS-SIDECAR

Delegation and admissibility are not competing systems.
They are complementary inputs to a complete governance
decision.

The most complete architecture passes the delegation chain
as an input to the admissibility evaluation:

    Identity system produces:
      Delegation chain D
        (User → Agent A → Agent B → Tool Y,
         cryptographically signed, full chain)
            ↓
    Admissibility evaluation receives:
      D + Proposed action + Constraint set
            ↓
    Gate evaluates:
      Is the action admissible?
      Is every actor in D authorized for this action scope?
      Does the chain authority cover this consequence class?
            ↓
    Outcome: A = ALLOW | DENY
            ↓
    CVS Evidence Object contains both D and A:
      Who called what (D)
      Whether it was admissible (A)
      Cryptographic proof of both

Now the gate evaluates action + authority chain + constraints.
A valid delegation chain with an inadmissible action: DENY.
A valid delegation chain with an admissible action but a
chain member not authorized for that action scope: DENY.
A valid delegation chain with an admissible action and full
chain authority: ALLOW.

---

### 6. The Complete Evidence Record

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION · CVS-SIDECAR

Five years after a security incident — in litigation,
in a regulatory examination, in an insurance claim —
the question is not only who called what. It is whether
the action was admissible, and whether that determination
can be independently verified.

An evidence record containing only D (delegation chain)
answers: this chain happened, every actor is identified.

An evidence record containing only A (admissibility
evaluation) answers: this action was evaluated, this
was the outcome, here is the proof.

An evidence record containing both answers: this chain
happened, every actor is identified, the action was
evaluated against this constraint set, the outcome was
this, and all of it is independently verifiable against
a public ledger without trusting the operator.

    WHO made the call?       (D — delegation chain)
    SHOULD it have existed?  (A — 512 gate evaluation)
    CAN it be proven later?  (CVS Evidence Object)

Neither D alone nor A alone is sufficient for liability,
insurance, or regulatory examination. Together they form
the complete evidentiary record that makes AI agent
actions governable by the same legal and actuarial
frameworks that govern every other consequential economic
action.

---

### 7. The Positioning Statement

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: DELEGATION-ADMISSIBILITY-DISTINCTION · 512-KERNEL · CVS-SIDECAR

Identity systems prove the delegation chain.
512 evaluates whether the requested action is admissible.
CVS produces a cryptographic receipt of the decision.

These are complementary layers. High-consequence AI
deployments will require all three. The integration point
is the authority chain: identity systems prove who called
what; that delegation chain should become an input to
the admissibility evaluation at the 512 gate.

The question shifts from:

    Who made the call?

To:

    Should the call have existed at all?

That is where the deeper governance, insurance, audit,
and infrastructure conversation starts.

> "Delegation ≠ Authority.
> Lineage is not authorization. A perfectly authenticated
> chain of custody for an inadmissible action is not a
> defense. It is a complete evidence record of a violation."
> — Jonathan M. Watson

---

### Relationships

Source: Jonathan M. Watson | 512 / CVS — Watson

This document depends on:
- core/512-kernel/512-overview.md
- core/cvs/cvs-overview.md
- primitives/execution-boundary.md
- primitives/refusal-primitive.md
- primitives/evidence-object.md
- kernel/INVARIANTS.md

This document is required by:
- applications/agentic-systems/agentic-governance.md
- applications/agent-economics/agent-economics.md
- articles/delegation-not-authority.md

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
