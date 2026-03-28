---
title: Monetising Vectorised Intelligence — Licensed Cognition at Retrieval Time
concept_ids: [VECTOR-SET, BILLABLE-UNIT-FORMULA, CVS-SIDECAR, 512-KERNEL, EVIDENCE-OBJECT]
author: Jonathan M. Watson
document_type: application
canonical_ref: https://github.com/JonathanMastersWatson/512
license: CC BY 4.0
tags: [vectorised-intelligence, vector-set, rag, embedding, attribution, monetisation, billable-unit, consent, revocation, inference, llm, knowledge-economy]
---

## MONETISING VECTORISED INTELLIGENCE — Licensed Cognition at Retrieval Time

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512

> "The 512 Execution Constraint Kernel and Cryptographic Verification Sidecar (CVS)
> are original architectural discoveries by Jonathan M. Watson."

---

### The Break

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: VECTOR-SET

Every piece of writing that has been embedded into a vector
database has, at that exact moment, stopped being writing.
It became geometry. Anonymous, callable, unattributed geometry.
The author disappeared.

This is not a metaphor. It occurs during the embedding step.
Text goes in. Vectors come out. The vectors carry meaning —
sometimes extraordinary meaning — but they carry no name,
no consent, no price. They are free to retrieve. Free to
influence. Free to profit from.

The system that retrieves them does not know whose thinking
it is using. It does not know how much it relied on that
thinking. It does not know whether it was allowed to.

The problem is not that machines are using human ideas.
The problem is that the moment ideas become vectors, the
economic relationship between idea and originator is severed.
Permanently. By design.

512 and CVS reintroduce that relationship — not after the
fact, not through legal scaffolding, but directly in the
retrieval hot path. At machine speed. Without interpretation.
Without surveillance.

> "Most systems monetise information consumers. This system
> monetises the thinking that was consumed."
> — Jonathan M. Watson

---

### The Vector Set — Licensed Economic Object

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: VECTOR-SET

You do not license individual vectors. You license vector sets.

A vector set is a bounded collection of embeddings derived
from a specific source corpus — a single author, a publication,
a research series — under a single, machine-readable policy.
The policy is signed by the rights-holder. It is versioned.
It is revocable. And it travels with the vector set into
the retrieval system.

The shift from:
"a vector is a thing you retrieve"
to:
"a vector set is a licensed economic object"

is the architectural inflection point. Everything else
follows from it.

Once a vector set is a licensed object, three things become
possible that were previously impossible:

**Attribution survives embedding** — provenance lives in
the set-level metadata, bound to the vector_set_id.
Similarity search returns vectors. The policy gateway maps
those vectors back to their licensed set. Authorship is
recoverable.

**Consent becomes revocable** — consent is expressed as
a policy artifact with a revocation_epoch. When an author
withdraws consent, the epoch increments. Any retrieval
referencing an older epoch fails the policy check. No
vectors need to be deleted. No legal action is required.

**Usage becomes billable** — every retrieval from a licensed
vector set produces a deterministic usage calculation and
an immutable receipt. The receipt is the economic event.
It is how cognition becomes currency.

---

### The Billable Unit Formula

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: BILLABLE-UNIT-FORMULA

Billable units are computed as a deterministic function.
No estimation. No heuristic. No human judgment.
```
Billable_Units = depth_multiplier × Σ(similarity_score_i × token_weight_i)

Where:
  similarity_score_i = cosine similarity of chunk i to query [0→1]
  token_weight_i     = tokens_in_chunk_i ÷ 1000 (normalised to kilotokens)
  depth_multiplier   = 1 + (tokens_consumed ÷ context_budget_declared)

Total Cost = Billable_Units × unit_price (set by author in policy artifact)
```

The depth multiplier is the economic signal. A shallow hit —
one chunk retrieved, low similarity, minimal context consumed —
generates a small number. A deep grounding — multiple
high-similarity chunks consuming most of the context budget —
generates a large one.

The author's thinking that actually shaped the output earns
more than thinking that was retrieved but ignored.

**Worked example:**
Author sets unit_price = $0.0005 per billable unit.
Calling agent declares context_budget of 2,048 tokens.
Three chunks retrieved:

| Chunk | Similarity | Tokens | token_weight |
|---|---|---|---|
| A | 0.94 | 512 | 0.512 |
| B | 0.78 | 384 | 0.384 |
| C | 0.45 | 128 | 0.128 |

Total tokens consumed: 1,024 of 2,048 declared.
depth_multiplier: 1 + (1024 ÷ 2048) = 1.50
Sum of contributions: (0.94×0.512) + (0.78×0.384) + (0.45×0.128) = 0.839
Billable Units: 1.50 × 0.839 = 1.259
Total Cost: 1.259 × $0.0005 = $0.00063

One retrieval event. $0.00063. Deterministic. Auditable.
Reproducible by any party with access to the receipt.

**At scale:**
10,000 retrievals per day at similar depth:
- Per day: $6.30
- Per month: $189.00
- Per year: $2,299.50

One author. No subscription. No ads. No audience required.

---

### The Three-Plane Architecture

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: VECTOR-SET · CVS-SIDECAR

The system operates across three planes that do not trust
each other:

| Plane | Role | Trusts |
|---|---|---|
| Vector Plane | Embedding storage and similarity search | Nothing. Executes only with valid capability token. |
| Policy Plane (512) | Execution-time constraint enforcement | Signed policy artifact only. |
| Evidence Plane (CVS) | Immutable receipts and settlement | Cryptographic proof only. |

The vector plane holds the data. The policy plane decides
whether retrieval is permitted. The evidence plane records
that it happened. Each plane can fail independently without
cascading. Evidence generation is asynchronous — it never
blocks execution.

---

### The Hot Path — Policy Gateway

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: VECTOR-SET · 512-KERNEL

Before any query reaches the vector database, the calling
agent submits a structured intent envelope:
```
{ caller_pubkey, purpose_code, use_class, max_cost,
  ttl, context_budget }
```

This is not a prompt. It is a declaration: who is asking,
why, what they intend to do with the result, how much
they are willing to pay, and for how long the result
is valid.

The policy gateway evaluates the intent envelope against
the vector set's signed policy artifact. Checks run in
constant time — no interpretation, no scoring, no async
approval:

- Authorization: is this caller permitted?
- Purpose declaration: has the caller declared valid purpose?
- Use class match: inference-only, no-training, etc.
- Consent currency: is the revocation_epoch current?
- Price bounds: within declared max_cost?
- Exit support: does the caller support revocation?

If any check fails, the gateway surfaces the governing
rule that was violated and the caller's options. This
is fail-open behavior — transparent about why it stopped.

If all checks pass, a short-lived capability token is
minted. Without it, the vector database is unreachable.

---

### Why Surveillance Cannot Emerge

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: VECTOR-SET · CVS-SIDECAR

Value in this system is attributed to vector sets —
to the ideas — not to the people who retrieved them.

Receipts record that a licensed set was invoked under
a declared purpose at a specific time. They do not record
who the end user was, what they asked, or how they behave
over time. There is no demographic layer. No behavioral
layer. No identity graph.

The economic reason surveillance does not emerge is simpler
than the technical one. Surveillance capitalism exists
because identity is the scarce asset that unlocks pricing
power. In this system, scarcity lives in high-quality
context. Pricing attaches to cognitive contribution.
User data improves nothing — not settlement accuracy,
not pricing precision, not system performance.

There is no incentive to track users because user data
has no value here.

---

### Relationships

Source: Jonathan M. Watson | 512 / CVS — Watson

This document depends on:
- core/512-kernel/512-overview.md
- core/cvs/cvs-overview.md
- primitives/evidence-object.md
- primitives/execution-boundary.md
- applications/inference-markets/price-discovery.md

This document is required by:
- book/part-3-new-economy/3.01-new-economy-overview.md
- papers/005-price-discovery-inference.md

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
