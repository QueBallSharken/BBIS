# BBIS Canonical Foundation (Revised)

## Status

**BBIS** means **Boundary-to-Boundary Invariant Survival**.

This document is a revised foundation artifact. It does not replace the shorter canonical definition already in the repository. It extends and formalizes that doctrine so the development path is visible.

BBIS is **not** a concrete architecture, control surface, or implementation stack. BBIS is a **continuity requirement** and an **evaluation criterion**. It asks whether the same governing invariant remains live, binding, and refusal-capable across every mutation-capable boundary in scope until the true irreversible mutation authority.

A system satisfies BBIS within scope only if the governing invariant survives the full governed mutation path to the true irreversible commitment point without semantic weakening, substitution, loss of refusal authority, or loss of verifiable continuity.

---

## Abstract

This document defines the canonical foundation of BBIS through six questions: the ontology of governance invalidity, the primitive at which invalidity must be blocked, the scope of non-expressibility, the representation and enforcement of admissibility across translation layers, the distinction between impossibility and mere monitoring, and the completion criterion when full structural inadmissibility is not achievable.

The central claim is precise. A terminal state may be semantically correct, operationally coherent, and locally policy-valid, yet still be governance-invalid because the realization path that produced it was not continuously governed. BBIS is concerned with that continuity condition. It does not ask only whether a final state "looks valid." It asks whether the governing invariant remained continuously bound to the full mutation path and was still mechanically capable of refusal at the true irreversible mutation authority.

The result is a framework for distinguishing strong bounded governance from partial governance, detectable-only governance, and governance theater.

---

## 1. Core Principle

A governed transition is not valid merely because it was authorized earlier, executed faithfully, or recorded completely. It is valid only if the same governing invariant survives each mutation-capable boundary in scope as a live refusal condition until the true irreversible mutation authority.

That principle yields four consequences.

1. **State validity is not sufficient for governance validity.**
2. **Upstream approval is not sufficient for downstream commitment legitimacy.**
3. **Local refusal does not imply end-to-end non-expressibility.**
4. **Evidence must show continuity at the true commitment boundary, not merely prior intent or approval.**

---

## 2. Ontology of Governance Invalidity

BBIS requires a distinction between defects in the state itself and defects in the way the state was produced.

### 2.1 Invalid state

An **invalid state** is a machine-representable system configuration that violates an explicitly encoded governing constraint. The relevant constraint may derive from semantic rules, operational rules, policy rules, authority rules, safety rules, or continuity rules.

An invalid state answers the question: **what is wrong with the resulting configuration?**

### 2.2 Invalid transition

An **invalid transition** is a state change that violates governing constraints on the movement from one state to another, even if the initial and terminal states each appear valid when evaluated separately.

An invalid transition answers the question: **what is wrong with the state change itself?**

### 2.3 Invalid realization

An **invalid realization** exists when a terminal state is semantically and operationally acceptable in isolation, but the path that produced or committed it was governance-illegitimate. The defect lies in the realization path, commitment event, authority chain, continuity condition, or evidence chain.

An invalid realization answers the question: **what is wrong with how this state came to exist?**

This is the BBIS-critical category.

### 2.4 Inadmissible mutation

An **inadmissible mutation** is a proposed state-changing operation that the architecture must refuse before commitment because it would produce an invalid state, an invalid transition, or an invalid realization.

An inadmissible mutation answers the question: **what must be blocked before commitment occurs?**

### 2.5 Canonical distinction

A state can be:

- semantically valid,
- operationally valid,
- locally policy-valid,
- and still governance-invalid.

That occurs when the governing invariant did not remain continuously bound to the mutation path that produced the state.

### 2.6 Minimal formal schema

Let:

- `S` = state configuration
- `Δ` = state change
- `G` = governing constraint set
- `B` = boundary context
- `P` = path history
- `T` = time index
- `E` = evidence set
- `M` = mutation record

Then:

- `InvalidState(S, G, B, P, T, E)`
- `InvalidTransition(Δ, G, B, P, T, E)`
- `InvalidRealization(S, G, B, P, T, E, M)`
- `InadmissibleMutation(M_attempt, G, B, S_current)`

with the canonical relation:

```text
InadmissibleMutation(M) ↔
  InvalidState(Commit(M), G, B, P, T, E)
  ∨ InvalidTransition(M, G, B, P, T, E)
  ∨ InvalidRealization(Commit(M), G, B, P, T, E, M)
```

and the BBIS-critical asymmetry:

```text
InvalidRealization(S, ...) → ¬InvalidState(S, ...) may still hold.
```

In plain terms: the state may look valid while the realization remains illegitimate.

---

## 3. The Primitive at Which Invalidity Must Be Blocked

### 3.1 Relative meaning of primitive

A **primitive** is the smallest operational unit at which the governance property in question can still be independently enforced, lost, transferred, or verified. Primitive does **not** mean metaphysically smallest in all decompositions. It means irreducible **relative to the governance property under examination**.

For BBIS, the critical primitive is the last unit at which refusal is still mechanically possible before irreversible commitment.

### 3.2 Primitive hierarchy

| Level | Primitive | Governance question |
|---|---|---|
| 1 | Semantic primitive | Can the invalid form be represented? |
| 2 | Execution primitive | Can it be dispatched or activated? |
| 3 | Mutation primitive | Can it alter state? |
| 4 | Irreversible primitive | Can refusal still prevent final commitment? |
| 5 | Authority primitive | Is authority still valid, attenuated, and constitutive of commitment? |

### 3.3 First expressibility versus final commitment

Invalidity may become representable well before it becomes commit-capable.

- At early layers, invalidity may be **expressible**.
- In mid-path layers, invalidity may be **dispatchable or mutation-capable**.
- At the true irreversible primitive, invalidity becomes either **refused** or **irreversibly committed**.

BBIS is not satisfied merely because invalidity was checked upstream. It is satisfied only if the governing invariant remains live and refusal-capable at the true irreversible mutation authority.

### 3.4 Misidentification failure

A governance claim collapses if the claimed control point is upstream of the true irreversible primitive.

Examples:

- a local database write is not the true primitive if downstream consensus decides durable commitment,
- an API call is not the true primitive if the receiving system performs the actual irreversible mutation,
- a software-side confirmation is not the true primitive if a later physical actuator commit makes refusal impossible.

### 3.5 Authority primitive

Authority is not present merely because authorization existed somewhere in the system. For BBIS, authority matters only when it is still valid and mechanically verified at commitment.

A serious authority primitive requires:

- valid issuance,
- bounded scope,
- attenuation preservation,
- revocation sensitivity,
- time validity,
- object binding,
- version binding,
- parameter binding,
- and commitment-time verification.

If authority was checked earlier but not at the true irreversible primitive, the governance claim is weakened or lost.

---

## 4. Non-Expressibility: Local, Path, and End-to-End

### 4.1 Canonical definition

A condition is **non-expressible within scope** iff no admissible mutation path in the claimed scope can carry it to the true irreversible mutation authority as a commit-capable state transition.

This definition is stricter than "not usually observed" and stricter than "screened out by an upstream layer."

### 4.2 Levels

| Level | Meaning |
|---|---|
| Local non-expressibility | Invalidity cannot be realized within one component’s operational scope |
| Path non-expressibility | Invalidity cannot be realized along one enumerated mutation path |
| End-to-end non-expressibility | Invalidity cannot be realized across the full mutation path in scope |
| Apparent non-expressibility | Invalidity appears blocked locally but remains realizable through bypass, alternate route, or latent path |

### 4.3 Non-composition rule

Local non-expressibility does not automatically compose into path non-expressibility. Path non-expressibility does not automatically compose into end-to-end non-expressibility.

Composition requires:

- path inventory,
- invariant preservation across handoffs,
- containment or elimination of alternate mutation routes,
- absence of downstream ungoverned commit points,
- authority continuity,
- and evidence continuity.

### 4.4 Common failure mechanisms

Local controls fail globally when invalidity can still travel through:

- alternate tool paths,
- retry routes,
- deferred execution,
- orchestration/executor splits,
- downstream services with independent authority,
- ambient credentials,
- maintenance or recovery modes,
- human override paths,
- physical side channels.

### 4.5 Ideal and practical formulations

The theoretical target is universal:

```text
NonExpressible_ideal(S, G, System) ↔
  ∀ mutation_paths m:
    Commit(m) = S → MechanicalRefusal(m) ∨ SyntacticImpossibility(S) ∨ ¬BypassPath(m, S)
```

In open systems, that universal quantification is usually unattainable as a fully proved claim.

The practical bounded form is:

```text
NonExpressible_bounded(S, G, Scope, Verifier) ↔
  Verifier shows that every enumerated mutation path in Scope refuses S,
  all known bypass paths in Scope are blocked or contained,
  and out-of-scope residual risk is explicitly declared.
```

BBIS operates primarily in this second regime.

---

## 5. Admissibility Across Translation Layers

### 5.1 Translation is a governance boundary

A **translation layer** is any boundary-crossing transformation that changes encoding, semantics, protocol, authority form, execution model, or evidence format while preserving downstream causal power.

Translation is not a neutral pipe. It is a potential invariant-loss surface.

### 5.2 Translation types

| Type | What changes | Risk |
|---|---|---|
| Semantic translation | Meaning of the operation or constraint | Divergence in what the operation actually means |
| Schema translation | Structure, fields, types, precision | Field loss, widening, optionalization |
| Protocol translation | Delivery semantics, retries, timing, idempotency | Timing drift, duplicate execution, altered commitment semantics |
| Authority translation | Capability format, attenuation, delegation chain | Widened or truncated authority |
| Execution translation | Concurrency, isolation, transaction behavior | Atomicity shifts, race conditions |
| Evidence translation | Proof structure, attestation format, log form | Loss of replay or verification ability |

### 5.3 Canonical representation requirement

Admissibility must be represented in a form that can survive translation without silent weakening. Strong forms include:

- canonical constraint objects,
- capability-bound authorization artifacts,
- signed canonical structures,
- executable guards,
- proof-carrying bundles.

Natural-language intent is insufficient as the governing form at commitment.

### 5.4 Translation failure modes

The invariant may be lost through:

- weakening,
- widening,
- narrowing,
- substitution,
- omission,
- reinterpretation,
- context loss,
- time drift,
- authority drift,
- evidence drift.

### 5.5 Preservation requirements

For BBIS within scope, a translation layer must preserve:

1. **canonical invariant identity**,
2. **explicit field semantics**,
3. **object binding**,
4. **version binding**,
5. **parameter binding**,
6. **authority continuity**,
7. **time validity**,
8. **refusal semantics**,
9. **evidence continuity**,
10. **replayability or reconstructability sufficient for verification**.

### 5.6 Downstream verification requirement

A downstream mutation-capable layer is governed only if it verifies, before acting:

- canonical admissibility form,
- invariant identity,
- object/version/parameter match,
- authority validity,
- temporal validity,
- proof or evidence completeness sufficient for the layer’s role,
- and refusal behavior on verification failure.

If the downstream layer executes on ambient authority or on locally well-formed commands without invariant verification, it is a dumb endpoint relative to BBIS.

---

## 6. Impossibility, Bounded Impossibility, and Theater

### 6.1 Canonical distinction

Different proof-strength claims establish different things.

| Claim type | What it honestly means |
|---|---|
| Formal impossibility | The invalidity is excluded in the formal model |
| Bounded impossibility | The invalidity is excluded within explicit operational bounds |
| Practical bounded non-expressibility | Enumerated paths in scope are blocked or refusal-capable, with declared residual risk |
| Monitoring claim | Invalidity is detectable after expression |
| Mitigation claim | Invalidity can be responded to after commitment |
| Probabilistic safety claim | Invalidity is unlikely, not structurally excluded |
| Auditability claim | The event can be reconstructed after the fact |

These are not interchangeable.

### 6.2 What theater is

Governance theater exists when the language of impossibility, prevention, or end-to-end governance is used to describe what is actually only:

- monitoring,
- mitigation,
- probabilistic reliability,
- retrospective reconstruction,
- or upstream control displaced downstream.

### 6.3 Trust-base limit

Every proof regime bottoms out in a trusted base: a proof assistant, model checker, verifier, hardware assumption, cryptographic base, or social/organizational trust statement.

BBIS does not eliminate that limit. It requires it to be stated honestly.

### 6.4 What a serious bounded claim requires

A serious bounded claim requires all of the following:

1. explicit scope,
2. identified primitives,
3. mutation-path inventory in scope,
4. canonical invariant representation,
5. downstream enforcement at all mutation-capable commitment points in scope,
6. bypass closure or explicit bounded residual risk,
7. evidence that refusal remained live at the true commitment boundary,
8. explicit strongest non-claim.

### 6.5 Impossibility versus continuity evidence

These two must be separated.

- **Impossibility proof** concerns whether invalidity is structurally excluded within a defined model or scope.
- **Continuity evidence** concerns whether a specific governed execution preserved the invariant through the actual path to commitment.

BBIS depends on both questions, but they are not the same question.

A system may lack universal impossibility proof and still provide strong continuity evidence for bounded governed execution. Conversely, a system may prove local exclusion properties while failing to show end-to-end continuity at commitment.

---

## 7. Completion Criterion When Full Structural Inadmissibility Is Not Achievable

### 7.1 Canonical categories

| Category | Meaning |
|---|---|
| Full structural inadmissibility | Invalidity is non-expressible across all mutation paths in all relevant substrates with no residual expressibility |
| Bounded end-to-end governance | Invalidity is non-expressible within explicit scope; outside scope, residual risk is declared |
| Partial governance | Some paths or boundaries are governed, others are not |
| Detectable-only governance | Invalidity is expressible; the system relies on retrospective detection or response |
| Governance theater | Prevention or bounded governance is claimed where only detection, displacement, or vague controls exist |

### 7.2 Completion criterion for honest bounded claims

A system may claim **complete within scope** only when all of the following hold within the declared scope:

1. every enumerated mutation path is governed end to end,
2. the true irreversible mutation authority is correctly identified,
3. the governing invariant remains live and refusal-capable until that authority,
4. no in-scope bypass path reaches commitment without equivalent verification,
5. all translation layers preserve the invariant or refuse on failure,
6. authority remains valid, bounded, and verified at commitment,
7. evidence demonstrates continuity at the commitment boundary,
8. strongest non-claims and residual risk are explicitly stated.

### 7.3 Partial versus theater

A system is **partial** when it honestly declares which paths, objects, or operations are governed and which are not.

A system is **theater** when:

- the scope is implicit or overstated,
- the true primitive is misidentified,
- ungoverned in-scope paths are hidden,
- downstream commitment occurs without invariant verification,
- or monitoring is presented as prevention.

### 7.4 Completion statement template

The strongest honest completion statement has this form:

> This system provides bounded end-to-end governance for the declared object types, operations, paths, and trust assumptions in scope. Within that scope, the governing invariant remains live and refusal-capable to the true irreversible mutation authority, and evidence supports continuity at commitment. No broader claim is made.

### 7.5 Strongest non-claim template

A serious artifact should also state:

> This system does not claim universal structural inadmissibility, governance outside the declared scope, continuity across undeclared translation paths, or prevention where only detection, mitigation, or retrospective reconstruction exists.

---

## 8. BBIS Classification Rule

The BBIS classification of a system is determined by the strongest claim it can honestly support.

### 8.1 Strong

A system is **BBIS-Strong within scope** only if it demonstrates:

- complete in-scope mutation-path inventory,
- canonical invariant preservation across translations,
- live refusal at the true irreversible mutation authority,
- bypass closure within scope,
- and evidence showing continuity at commitment.

### 8.2 Partial / bounded

A system is **BBIS-Partial** when those conditions hold only for a declared subset of objects, operations, paths, or substrates, with explicit residual risk and non-claims outside that subset.

### 8.3 Detectable-only

A system is **BBIS-Detectable-Only** when invalidity remains expressible at the true authority and the system offers only monitoring, reconstruction, reconciliation, or response.

### 8.4 Fail

A system **fails BBIS** when it claims prevention or continuity without live refusal at the true authority, without credible path inventory, without preserved invariant identity across translations, or while relying on hidden bypasses or ambient authority.

---

## 9. Open Problems

Several problems remain open even under a disciplined BBIS framing.

1. **Completeness of path inventory.** Open systems rarely permit proof that all mutation paths are known.
2. **Translation faithfulness across domains.** Shared invariant identity across heterogeneous systems is difficult to formalize.
3. **Temporal validity.** Revocation, expiry, replay windows, and clock-domain mismatch remain hard.
4. **Composition.** Two locally governed systems do not automatically compose into a BBIS-governed whole.
5. **Verifier regress.** Every verification regime bottoms out in a trusted base.
6. **Human override.** Discretionary human intervention reintroduces expressibility unless explicitly modeled and bounded.
7. **Physical coupling.** Software-side governance does not guarantee material-world non-expressibility.
8. **Dynamic scope drift.** Updates, maintenance modes, failure paths, and configuration change can move a system outside its declared scope.

These do not invalidate BBIS. They define the frontier at which claims must narrow, assumptions must be declared, and stronger evidence is still required.

---

## 10. Canonical Definition

**Boundary-to-Boundary Invariant Survival (BBIS)** is a continuity requirement and evaluation criterion for governed mutation systems.

BBIS requires that the same governing invariant remain live, binding, and refusal-capable across every mutation-capable boundary in the declared scope until the true irreversible mutation authority. A system satisfies BBIS within scope only if the invariant survives translation, delegation, execution, and commitment without semantic weakening, substitution, loss of refusal authority, or loss of verifiable continuity.

BBIS is not itself a concrete architecture. It does not prescribe a specific token format, enforcement mechanism, verifier design, protocol, cryptographic suite, or implementation stack. Instead, it defines the condition that any such architecture must satisfy in order to make a serious claim of governed continuity.

The BBIS-critical failure mode is **invalid realization**: a terminal state that appears valid in isolation but is governance-invalid because the invariant did not remain continuously bound to the realization path and the true commitment boundary.

---

## 11. Practical Evaluation Questions

Any serious BBIS evaluation should answer, at minimum, the following questions.

1. What is the governing invariant?
2. What is the true irreversible mutation authority?
3. Which mutation-capable boundaries exist in scope?
4. Which of those boundaries are refusal-capable?
5. How is invariant identity represented canonically?
6. How is authority bound to object, version, and parameters?
7. How is invariant continuity preserved across translation layers?
8. Which alternate or bypass paths remain, if any?
9. What evidence proves continuity at commitment?
10. What is the strongest honest claim, and what is the strongest honest non-claim?

If these questions cannot be answered precisely, the governance claim is weaker than it appears.

---

## 12. Final Statement

BBIS does not ask whether a system has many controls. It asks whether the governing invariant actually survives the full mutation path to the point where refusal finally ceases to be possible.

That is the difference between local correctness and governed continuity, between approval and commitment legitimacy, and between real bounded governance and governance theater.
