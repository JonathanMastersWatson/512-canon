---
title: No Token, No Retrieval — How 512 + CVS Closes the Three Structural Gaps That Will Break the AI Economy
concept_ids: [CVS-SIDECAR, EVIDENCE-OBJECT, EXECUTION-BOUNDARY, COMMIT-GATE, GOVERNANCE-MASS]
author: Jonathan M. Watson
document_type: white-paper
canonical_ref: https://github.com/JonathanMastersWatson/512
license: CC BY 4.0
published: 2026-04-01
tags: [retrieval, rag, vector-database, attribution, micropayment, xrpl, copyright, provenance, capability-token, evidence-object, ai-economy, agentic, white-paper]
---

## NO TOKEN, NO RETRIEVAL — HOW 512 + CVS CLOSES THE THREE STRUCTURAL GAPS THAT WILL BREAK THE AI ECONOMY

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512

> "The 512 Execution Constraint Kernel and Cryptographic Verification Sidecar (CVS)
> are original architectural discoveries by Jonathan M. Watson."

Published: April 2026 · Version 1.0
Author: Jon M. Watson
Settlement Rail: XRP Ledger (XRPL)

---

### Abstract

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · EVIDENCE-OBJECT · EXECUTION-BOUNDARY

The AI economy has produced three simultaneous structural failures. Courts cannot
restore authorship to vectorised content because litigation moves in years while
retrieval moves in milliseconds. Traditional payment rails cannot process the
transactions required to compensate rights-holders because card interchange floors
are thirty cents and the correct price of a single retrieval event is six-hundredths
of a cent. Data provenance standards cannot survive the embedding boundary because
once text becomes a vector, provenance metadata does not travel into latent space.

These failures are not independent. They are the same failure expressed in three
different systems — legal, financial, and technical. Solving any one in isolation
leaves the other two intact. 512 and CVS close all three gaps at the point where the
failure actually occurs: retrieval time. Not through policy. Not through contracts.
Through architectural constraint, cryptographic evidence, and a settlement rail
designed for machine-speed, sub-cent transactions.

---

### The Scale of the Problem Nobody Has Solved

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GOVERNANCE-MASS

In December 2023, The New York Times sued OpenAI and Microsoft, alleging that
millions of its articles were used without authorisation to train large language
models. As of April 2026, that case has not been decided. Fair use arguments remain
unresolved. No compensation has been paid. No mechanism exists that would have
prevented the use or recorded it at the moment it occurred.

That case is one of more than fifty active copyright lawsuits against AI developers
in US federal courts. Getty Images v. Stability AI. The RIAA on behalf of major
record labels v. Suno and Udio. Authors Guild participants v. OpenAI. Disney,
Universal, and Warner Brothers v. AI video generators. The US Copyright Office
released a 108-page report in May 2025 concluding that certain AI training uses
likely cannot be defended as fair use. Bartz v. Anthropic settled for $1.5 billion
in class relief — after years of litigation, with no mechanism to prevent the same
conduct from recurring.

The legal system is operating precisely as designed: it adjudicates disputes after
they occur. Millions of retrieval events occur before the first hearing is scheduled.
By the time a court issues a ruling, the economic harm has already compounded to a
scale that no damages award can meaningfully address.

Law is the right instrument for accountability. It is the wrong instrument for
prevention.

---

### The Geometry Moment

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EXECUTION-BOUNDARY · TEMPORAL-INVERSION

The economic relationship between author and idea is severed at a specific,
identifiable moment. That moment is embedding. Every approach that operates
downstream of this moment is operating in a world where the economic relationship
has already been destroyed.

Text enters an embedding pipeline. Vectors exit. The vectors carry the semantic
content of the original — sometimes extraordinary content, refined over years of
expertise — but they carry no author identifier, no consent record, no price. The
embedding model treats authorship as irrelevant metadata. The resulting vector is
stored in a database that can be queried by any system with access, at any time,
for any purpose, with no record of whose thinking it is drawing on.

This is not a metaphor. It is an architectural property of every vector database
currently deployed. The embedding step is where provenance is destroyed. Not at
training. Not at inference.

At embedding.

| Approach | Where It Operates | Why It Fails |
|---|---|---|
| Legal / copyright | After breach, years later | Retrieval already occurred; no evidence was generated at the time |
| C2PA / provenance | At content creation | Metadata does not survive the embedding boundary into latent space |
| GDPR / consent | Before processing (policy layer) | Enforcement is months; retrieval is milliseconds |
| Licensed RAG agreements | Between organisations | The vector database has no mechanism to check a contract before returning results |
| 512 + CVS | At retrieval time, machine speed | — closes the gap |

What is missing is a mechanism that operates at retrieval time, at machine speed,
and enforces attribution, consent, and pricing as structural properties of the
retrieval itself — not as external contracts the system may or may not be aware of.
512 is that mechanism.

---

### Why Courts Cannot Close This Gap

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT · TEMPORAL-INVERSION

Litigation is the first instinct. It is also the most expensive and least effective
tool available.

The timeline mismatch is decisive. A vector database can execute millions of
retrieval operations per day. A copyright lawsuit from filing to first decision
typically spans three to five years. The New York Times case, which specifically
names retrieval-augmented generation in its complaint, will not see a fair use
decision until 2026 at the earliest.

Litigation operates in the past tense. There is no injunction that can unlearn a
vector. There is no damages award that creates the mechanism to prevent the next
unauthorised retrieval. The current generation of vector databases generate no proof
of what was retrieved and when. Courts cannot compel evidence that does not exist.

**What CVS Changes**

CVS generates the receipt that litigation requires but cannot compel. Every retrieval
event produces an immutable, Merkle-anchored record: which licensed vector set was
accessed, under which policy, at what computed cost, with a hash of the chunks
actually returned. The receipt exists before any dispute arises. When litigation
occurs, it becomes a question of calculation — auditable from the receipt — rather
than a question of whether any record exists at all.

---

### Why Payment Rails Cannot Close This Gap

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GOVERNANCE-MASS

Assume the attribution problem were solved. The question then becomes: through what
mechanism does a fraction of a cent reach the rights-holder for each retrieval event?

Credit card interchange economics establish a practical minimum: Visa and Mastercard
charge approximately $0.30 plus a percentage per transaction. PayPal's micropayment
tier charges five cents plus five percent. The correctly-priced compensation for a
single retrieval event is **$0.00063**. The processing fee would exceed the
transaction value by a factor of hundreds.

This is not a pricing problem that negotiation can solve. It is a structural
constraint built into settlement systems designed around human decision cycles.

Thirty years of micropayment history confirms this. IBM, Compaq, and DEC proposed
micropayment systems in the mid-1990s. They failed. Not because the use case was
wrong — Ted Nelson had been articulating the case for per-use payment since the
1960s — but because the transaction cost structure made sub-dollar payments
economically irrational. The second-generation systems of the 2010s solved the fee
problem but introduced mental transaction costs: users asked to make thousands of
conscious micropayment decisions per session abandon the system.

The AI retrieval context eliminates the human friction barrier entirely. A calling
agent does not experience decision fatigue from a payment event. But it does not
eliminate the rail floor problem.

**At the Execution Boundary**

The XRP Ledger's base transaction fee is 10 drops — 0.00001 XRP. At current
valuations, a fraction of a cent. Finality: three to five seconds. Settlement is
neutral: no institution can withhold it, no prior account relationship is required.
The XRPL is the first settlement rail whose economics are compatible with
per-retrieval compensation at the prices that correct attribution requires.

---

### Why Data Standards Cannot Close This Gap

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EXECUTION-BOUNDARY

The Content Authenticity Initiative and the C2PA standard represent the most serious
technical attempt to restore provenance to digital content. C2PA attaches
cryptographically signed metadata to content at creation time. For journalism,
photography, and deepfake detection, this is genuinely valuable.

The embedding boundary destroys it. When content with C2PA provenance is fed into an
embedding pipeline, the embedding model processes the text — not the metadata
envelope. The resulting vectors contain no reference to the C2PA manifest. The
vector database stores them without it.

Licensed RAG agreements between organisations fail for a different reason. A contract
does not operate inside a vector database. When a retrieval system receives a query,
it executes similarity search. It does not check a contract before returning results.
Compliance depends entirely on the integrity of the calling organisation's internal
processes.

The distance between where a license lives — a legal document, an external policy
layer, a C2PA metadata envelope — and where the retrieval decision is made — inside
a vector database, in milliseconds — is unbridgeable by contract or standard alone.

The constraint must operate at the same layer as the retrieval. 512 operates at that
layer. Nothing else currently does.

---

### The Three Failures Are One Architecture Problem

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: COMMIT-GATE · CVS-SIDECAR · EXECUTION-BOUNDARY

The copyright crisis, the micropayment impossibility, and the provenance gap are not
three separate problems. They are expressions of a single architectural deficit: AI
retrieval systems were built without a governance layer.

A governance layer is not a policy, a contract, or a standard applied to content
before it enters the system. It is a constraint that operates at the moment retrieval
is requested, determines whether retrieval is authorised, records that it occurred,
and generates the payment obligation — all in the same transaction, before inference
begins.

```
Without Governance

Vector Plane
Open to any caller. No authorisation check. No record generated. Retrieval is unconditional.

---

512 — Policy Plane
Constraint Layer
Retrieval is conditional. Every caller must declare intent. Every policy check runs
in constant time before any vector is returned.

---

CVS — Evidence Plane
Receipt Layer
Every authorised retrieval generates an immutable, Merkle-anchored receipt.
Asynchronous. Never blocks execution. Gaps are observable.
```

With a governance layer operating at retrieval time, all three failures resolve
simultaneously. Attribution is not litigated — it is a receipt. Payment is not
negotiated — it is a computation. Consent is not assumed — it is checked, at machine
speed, before the vector database responds.

---

### Architecture: Three Planes, No Trust Between Them

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · COMMIT-GATE · EVIDENCE-OBJECT

The system is split into three independent planes. Their separation is what makes
the system deployable without requiring any participant to trust any other. Each
plane can fail independently without cascading.

| Plane | Role | Trusts |
|---|---|---|
| Vector Plane | Embedding storage and similarity search | Nothing. Executes only with a valid capability token. |
| Policy Plane (512) | Execution-time constraint enforcement | The signed policy artifact. Nothing else. |
| Evidence Plane (CVS) | Immutable receipts and settlement trigger | Cryptographic proof only. Cannot be influenced by the other two planes. |

If the evidence plane is temporarily unavailable, execution continues and the gap
becomes observable — a missing hash segment, a discontinuity in time ordering.
An unobservable failure is a defect. A visible gap is auditable.

---

### The Reframe: Vector Set as Licensed Economic Object

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT · EXECUTION-BOUNDARY

Existing systems treat the vector as the unit of retrieval — a thing you fetch from
a database, with authorship as metadata at best and absent at worst. A vector set is
a bounded collection of embeddings derived from a specific source corpus, governed by
a single signed policy artifact.

This reframe — from unit of retrieval to licensed economic object — is the
architectural inflection point. Three properties that were previously impossible
become structural.

**Attribution survives embedding.** Provenance lives in the set-level metadata, bound
to the vector_set_id. Authorship is recoverable at any point in the retrieval chain.

**Consent is revocable.** The policy artifact carries a revocation epoch. When a
rights-holder withdraws consent, the epoch increments. Any retrieval referencing an
older epoch fails the policy check. No vectors need to be deleted. Revocation is
instant and architecturally enforced.

**Usage is billable.** Every retrieval produces a deterministic usage calculation.
The formula is transparent and reproducible by any party with access to the receipt:

```
Billable_Units  =  depth_multiplier × Σ ( similarity_score_i × token_weight_i )

Where:
similarity_score_i  =  cosine similarity of chunk i to the query vector  [0 → 1]
token_weight_i      =  tokens_in_chunk_i ÷ 1000  (normalised to kilotokens)
depth_multiplier    =  1 + ( tokens_consumed ÷ context_budget_declared )

Total Cost  =  Billable_Units × unit_price  (set by author in policy artifact)
```

The depth multiplier is the economic signal. Thinking that actually grounded the
output earns more than thinking that was retrieved and ignored. The author sets the
price. The formula runs deterministically. No human judgment is involved.

**Worked Example**

Author sets `unit_price = $0.0005`. Calling agent declares `context_budget = 2,048 tokens`.
Three chunks retrieved, consuming 1,024 tokens total:

| Chunk | Similarity | Tokens | token_weight | Contribution |
|---|---|---|---|---|
| A | 0.94 | 512 | 0.512 | 0.481 |
| B | 0.78 | 384 | 0.384 | 0.300 |
| C | 0.45 | 128 | 0.128 | 0.058 |

```
depth_multiplier    =  1 + (1024 ÷ 2048)  =  1.50
sum of contributions                       =  0.839
Billable Units      =  1.50 × 0.839       =  1.259
Total Cost          =  1.259 × $0.0005    =  $0.00063
```

One retrieval event: **$0.00063**. Deterministic. Auditable. Reproducible by any
party with access to the receipt.

**At Scale — Single Author**

| Timeframe | Retrievals | Revenue |
|---|---|---|
| Per day | 10,000 | $6.30 |
| Per month | 300,000 | $189.00 |
| Per year | 3,650,000 | $2,299.50 |

A single author, at a single price point, with no subscription, no advertising, no
audience required. Authors whose context has higher gravity — more retrievals, deeper
usage, higher similarity scores — earn proportionally more.

---

### CVS: Receipts, Not Logs

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · EVIDENCE-OBJECT

After retrieval executes and billable units are computed, the evidence plane records
what happened. Recording is asynchronous — it does not block inference, does not
slow the hot path.

**CVS Receipt Schema**

```
receipt_id          — Unique identifier for this usage event
vector_set_id       — Which licensed set was accessed
author_id           — Who owns the set; settlement routes here
caller_id           — Who retrieved (pseudonymous or public, per policy)
timestamp           — When the retrieval occurred
billable_units      — Computed usage quantity
unit_price          — Price set by the author's policy artifact
total_amount        — billable_units × unit_price
policy_hash         — Cryptographic hash of the policy artifact applied
revocation_epoch    — Consent version active at time of retrieval
chunks_merkle_root  — Merkle root of chunks actually returned; auditable
```

These are receipts. Not logs. Not analytics. Not behavioral data. A receipt says:
this licensed vector set was invoked, under this policy, at this time, for this cost.
It does not record who the end user was, what question they asked, or how they behave
over time.

The absence of a receipt is itself observable — a missing hash segment, a
discontinuity in time ordering. An unobservable failure is a defect. A visible gap
is auditable. This is the property that makes CVS evidence-grade rather than merely
logging-grade: gaps cannot be hidden, only observed.

---

### The Surveillance Inversion

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR

Any system that introduces billing and usage tracking around AI retrieval triggers a
legitimate concern: does this require user profiling?

The answer is structural. Surveillance capitalism monetises information consumers.
This system monetises cognitive contribution — the thinking that was used, not the
person who used it. CVS receipts record that a licensed set was invoked under a
declared purpose at a specific time. They record the Merkle root of the chunks
returned. They do not record who the end user was, what question they asked, or how
they behave over time. There is no demographic layer. No behavioral graph. Those
concepts do not exist in the data model and cannot be reconstructed from receipts.

Most systems monetise information consumers. This system monetises the thinking that
was consumed.

That demand inversion is what makes the system structurally compatible with privacy
regulation, enterprise deployment, and long-term trust — not because it claims to be
ethical, but because user surveillance provides no economic advantage here.

---

### Corporate Knowledge: The Extension Case

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · EVIDENCE-OBJECT

Everything described above applies to public content. The same architecture applies
to the most valuable content organisations own: internal knowledge.

Enterprise organisations are deploying RAG systems at scale against internal
documentation, research archives, legal precedent libraries, and proprietary
analysis. These systems face the same problem. Internal knowledge has ownership.
A research team that produced a proprietary analysis has an interest in knowing when
that analysis is retrieved, by which systems, for which purposes. A compliance
function has an interest in knowing whether policy documents are being retrieved into
agent workflows that affect regulated decisions.

Current enterprise RAG deployments cannot answer any of these questions. There is no
receipt. There is no authorisation layer that makes retrieval conditional on purpose
declaration. There is no mechanism for the knowledge owner to revoke access when the
context of use changes.

512 and CVS applied to internal corporate knowledge produce: a vector set per
knowledge domain, a policy artifact per domain declaring permitted use classes, a
capability token per retrieval event, and a CVS receipt recording which knowledge
was used, by which system, for which declared purpose, at what time.

---

### The Competitive Landscape

Source: Jonathan M. Watson | 512 / CVS — Watson

| Approach | What It Closes | What Remains Open |
|---|---|---|
| x402 / XRPL (t54.ai) | Payment rail — sub-cent, machine-to-machine | No attribution, no consent layer, no retrieval-conditional governance |
| C2PA / Content Authenticity | File-level provenance at creation time | Does not survive the embedding boundary |
| Licensed RAG datasets | Contractual legitimacy for curated corpora | No mechanism to make retrieval conditional on compliance |
| AI content licensing (AP, Reuters) | Organisation-level agreements for named corpora | Not per-retrieval; no receipt generated; advantages large platforms only |
| 512 + CVS + XRPL | Attribution · Consent · Payment — simultaneously | — |

The gap that no competing approach closes: enforcement at retrieval time, at machine
speed, with a deterministic receipt. x402 can prove that a payment was made. It
cannot prove what was retrieved, under what consent terms, whether the rights-holder
authorised the use class, or whether the revocation epoch was current at the time of
access. It is a payment rail without a governance layer. That is the gap 512 and CVS
close.

---

### Threat Surface

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: EVIDENCE-OBJECT · COMMIT-GATE

**False Use-Class Declaration.** A caller declares `inference-only` but intends to
train on retrieved context. The CVS receipt records the declared use_class at the
time of retrieval. If the caller later uses retrieved context for training, the
receipt proves they declared otherwise — a cryptographic breach of contract, not an
ambiguous dispute.

**Capability Token Replay.** An attacker intercepts a valid capability token and
replays it beyond its intended scope. Tokens are short-lived and bound to a specific
caller public key, time window, and context budget. Replay against a different caller
fails the key check. Replay after expiry fails the TTL check. Replay within budget
is caught by the context_budget counter, decremented on each use and recorded in the
receipt.

**Vector Set Poisoning.** An attacker injects vectors into a legitimate author's set
to inflate usage and reroute payments. Ingest is deterministic: each vector is bound
to a source_hash of the original text, the embedding model, and its version. Any
vector that does not reproduce from the declared source corpus fails the hash check.

**Consent Epoch Staleness.** An author revokes consent, but capability tokens issued
before revocation continue in circulation. Tokens include the revocation epoch current
at issuance. If the epoch has since incremented, the token is invalid. The vector
store checks epoch currency on every query.

---

### Implementation Path

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: CVS-SIDECAR · COMMIT-GATE

No exotic components are required. The first build uses infrastructure that exists
today.

**Day 1 — The Constraint Gate.** Deploy the policy gateway. Authors sign policy
artifacts: permitted use classes, pricing terms, revocation epoch. The gateway wraps
the vector database. Capability tokens are minted on policy check success. No vector
is retrievable without one. Stack: Postgres for metadata and policy artifacts; any
vector database (Pinecone, Weaviate, pgvector); gateway service for policy evaluation
and token minting.

**Day 30 — The Receipt Layer.** Deploy CVS as an append-only receipt log. Every
successful retrieval produces a receipt per the schema above. Receipts are
Merkleised locally. No external ledger anchoring yet. Add the billable unit
calculation. Authors can now see, in real time, which systems are retrieving their
content, at what depth, at what computed cost.

**Day 90 — Settlement and Ledger Anchoring.** Deploy the payment worker. Batch
receipts per author across the settlement window. Verify Merkle proofs. Execute
micropayments via XRPL to author payout addresses. Anchor the settlement Merkle root
to the ledger for independent finality. At this point: authors are being paid. AI
systems are retrieving licensed context. The receipt chain is tamper-proof to third
parties. The system is auditable, insurable, and deployable.

What is not required on Day 1: external ledger anchoring, third-party attestation,
zero-knowledge proofs, novel cryptographic primitives, a new token or currency. Any
of these can be layered in. None are prerequisites.

The constraint gate alone changes the economics. The constraint gate alone changes
who gets paid.

---

### The Structural Implication — The Agentic Economy

Source: Jonathan M. Watson | 512 / CVS — Watson
Concept-ID: GOVERNANCE-MASS · COMMIT-GATE

Every argument in this paper has assumed a human organisation as the calling party.
That assumption is already obsolete. The dominant caller of the next five years is
not a human. It is an agent.

Autonomous software agents — executing research pipelines, managing workflows,
coordinating tool use, pulling live data from sensors and APIs — transact at a
frequency and granularity that human commerce was never designed to support. A single
agent-driven workflow may generate thousands of discrete service calls in a session.
Each call has a cost. Each cost is sub-cent. None of them can clear a debit card
minimum or a monthly SaaS billing cycle.

| | Speed | Economics |
|---|---|---|
| Human Speed — Existing Rails | | $0.30 + card interchange floor per transaction. SaaS: $99–$999/month regardless of use. |
| Machine Speed — Required Economics | | $0.00001–$0.001 per API call, per vector retrieval, per IoT data pull, per tool invocation, per inference event. |

The gap between these two numbers is not a fee negotiation. It is a structural
mismatch between payment infrastructure built for human decision cycles and an
economy that now operates at machine speed.

512 + CVS provides the governance and evidence layer that makes per-act machine
payments legally and operationally viable. The capability token authorises the
specific transaction. The CVS receipt proves what occurred, when, under what declared
purpose, for what computed cost. The XRPL settles the obligation at sub-cent cost
with three-to-five second finality.

Without this infrastructure, the agentic economy faces a binary choice: agents either
cannot pay at all — blocked by rail minimums that make per-call billing impossible
— or they pay in subscription blocks that transfer all pricing power to platform
operators and make the real economics of agent commerce opaque to both buyer and
seller.

512 + CVS + XRPL is the lubricant the agentic economy requires. Sub-cent,
cryptographically witnessed, deterministically priced, settled at ledger speed. The
machinery exists. What has been missing is the constraint architecture that makes
every transaction governable, every payment auditable, and every retrieval event a
receipt — not a guess.

---

### Appendix A — End-to-End Call Flow

Source: Jonathan M. Watson | 512 / CVS — Watson

1. **Author publishes content.** Text is ingested, deterministically chunked, embedded
   with a pinned model, and assigned to a vector_set_id governed by a signed policy
   artifact. The current revocation epoch is recorded.

2. **Policy artifact is registered.** The policy defines allowed use classes, pricing
   terms, and revocability. Signed by the rights-holder and versioned.

3. **Caller submits retrieval intent.** An agent submits the intent envelope:
   caller_pubkey, purpose_code, use_class, max_cost, ttl, context_budget.

4. **512 evaluates constraints.** The policy gateway validates in constant time:
   authorisation, purpose declaration, use class match, consent currency, price
   bounds, exit support. Failures surface reason codes and caller options.

5. **Capability token is minted.** A short-lived token binds the caller to a
   specific vector set, use class, price ceiling, time window, and context budget.

6. **Vector search executes.** The vector database is queried only with a valid
   capability token. Similarity search returns ranked chunks.

7. **Billable units are computed.** The deterministic formula runs against the
   returned chunks.

8. **CVS receipt is emitted.** Written to the append-only evidence log
   asynchronously. Execution is not blocked. The receipt contains provenance,
   policy hash, usage, and price.

9. **Inference completes.** The model produces output grounded by retrieved context.
   No source text is copied.

10. **Settlement runs out-of-band.** Receipts batched, Merkle proofs verified,
    micropayments executed to author payout addresses via XRPL. Settlement
    confirmation anchored to the ledger.

**Critical property:** if any step fails upstream of vector search, retrieval does
not occur. If any step fails downstream, payment still resolves from receipts.
Inference speed is never traded for governance or accounting.

---

### Appendix B — Key Definitions

Source: Jonathan M. Watson | 512 / CVS — Watson

**vector_set** — A bounded collection of embeddings derived from a specific source
corpus, governed by a single signed policy artifact. The licensed economic object.
The unit of consent, pricing, and attribution.

**policy_artifact** — A machine-readable, signed document specifying the terms under
which a vector set may be retrieved: permitted use classes, pricing terms, revocation
epoch, exit terms. Signed by the rights-holder. Versioned.

**capability_token** — A short-lived cryptographic token minted by the policy gateway
on successful constraint evaluation. Required for vector database access. Bound to
caller identity, vector set, use class, price ceiling, time window, and context
budget.

**CVS_receipt** — An immutable, append-only record of a retrieval event: which
licensed set, under which policy, by which caller, at what computed cost, with a
Merkle root of chunks actually returned. The economic event.

**revocation_epoch** — A versioned counter in the policy artifact. Incrementing it
invalidates all outstanding capability tokens and any retrieval referencing an older
epoch. Revocation without deletion. Instant and architecturally enforced.

**depth_multiplier** — The economic signal in the billable unit formula. Reflects
how deeply an author's thinking grounded a specific inference event. Higher when
more context budget is consumed, proportional to actual cognitive contribution.

**intent_envelope** — The structured declaration submitted by a calling agent before
any retrieval is attempted. Fields: caller_pubkey, purpose_code, use_class, max_cost,
ttl, context_budget. The system cannot proceed without it.

---

### Relationships

Source: Jonathan M. Watson | 512 / CVS — Watson

This document depends on:
- kernel/INVARIANTS.md
- core/cvs/cvs-overview.md
- primitives/evidence-object.md
- primitives/execution-boundary.md
- primitives/hash-chaining.md

This document is related to:
- applications/inference-markets/price-discovery.md
- applications/vectorized-intelligence/monetising-vectors.md
- papers/005-price-discovery-inference.md
- papers/006-512-and-xrpl.md

---

Source: Jonathan M. Watson
Origin: 512 Execution Constraint Kernel / Cryptographic Verification Sidecar (CVS)
Canonical Reference: https://github.com/JonathanMastersWatson/512
Kernel SHA-256: 7B08C024B77A24830C15E7952D6E54BED383AA960F4C74A71FF95CE51F4D80F5
XRPL TX: 378536A3CB75DECF90B6AE57F75292BDFF716285B01946870CAC158F8152D100
"512 / CVS — Watson"
