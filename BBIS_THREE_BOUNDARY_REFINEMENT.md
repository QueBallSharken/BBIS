BBIS THREE-BOUNDARY REFINEMENT

Boundary-to-Boundary Invariant Survival Operational Refinement

Author: Steven Kyle Hensley
Alias: Stevil
GitHub: QueBallSharken

STATUS

This document refines BBIS as a standalone continuity requirement.

It does not replace "BBIS_CANONICAL_DEFINITION.md".
It sharpens how strong BBIS claims must be made, tested, and classified.

It is not a complete architecture by itself.

---

1. PURPOSE

BBIS claims are too easy to fake if a system can say continuity exists without naming the exact boundaries where the governing invariant remained live and refusal-capable.

This refinement exists to make BBIS claims mechanical rather than performative.

It does so by requiring:

1. explicit identification of three distinct boundaries
2. explicit identification of who held refusal capability at each boundary
3. explicit recording of the governing invariant evaluation result at each boundary
4. a per-action trace sufficient to diagnose continuity, downgrade, or failure

---

2. DIRECT RULE

A system must not claim strong BBIS conformance unless it can explicitly identify, for the claimed action and scope, all three of the following:

1. Local refusal boundary
2. System-wide refusal boundary
3. True irreversible mutation authority

If the system cannot name all three, the stronger continuity claim must not survive.

---

3. REQUIRED THREE BOUNDARIES

3.1 Local Refusal Boundary

The local refusal boundary is the nearest concrete decision point at which the governing invariant is still live and the system can still refuse before the relevant downstream step executes.

This is the first meaningful refusal-capable boundary in the claimed path.

A system must be able to identify:

- where it is
- which actor owns it
- what invariant was evaluated there
- whether refusal remained mechanically effective there

3.2 System-Wide Refusal Boundary

The system-wide refusal boundary is the furthest point in the claimed system path at which the governing invariant still remains live and refusal-capable for the claimed action.

This boundary may be identical to the local refusal boundary in simple systems.
It may differ in multi-hop, federated, delegated, or forwarded systems.

A system must be able to identify:

- where system-wide refusal actually lived
- whether downstream actors re-evaluated the invariant or merely trusted an earlier decision
- whether revocation, delegation change, or parent-authority change in flight could invalidate the earlier decision

3.3 True Irreversible Mutation Authority

The true irreversible mutation authority is the actual boundary, mechanism, or primitive whose successful execution makes the relevant mutation operationally binding or irreversible for the claimed scope.

This is the boundary that matters most.

A system must be able to identify:

- what the true irreversible primitive is
- whether the governing invariant remained live up to the last pre-mutation point
- whether any earlier gate is being mistaken for the actual mutation authority

If the claimed covered boundary is not the true mutation authority, the stronger continuity claim must be downgraded or rejected.

---

4. DISTINCTNESS RULE

These three boundaries must be treated as analytically distinct even if, in a particular implementation, two or more of them collapse to the same concrete point.

A system must not assume that:

- local refusal automatically equals system-wide refusal
- system-wide refusal automatically equals mutation authority
- earlier authorization automatically survives until execution

The system must prove the relationship, not assume it.

---

5. PER-ACTION TRACE REQUIREMENT

A conformant BBIS claim must be accompanied by a per-action trace showing, at minimum:

- the action or transition identity
- the claimed scope
- the local refusal boundary
- the system-wide refusal boundary
- the true irreversible mutation authority
- which actor held refusal capability at each boundary
- the governing invariant identity at each boundary
- the evaluation result of that invariant at each boundary
- the timing relation between refusal capability and mutation completion
- whether the action was refused, allowed, downgraded, or left unverifiable

If this trace cannot be produced, the stronger continuity claim must not survive.

---

6. MINIMUM TRACE SHAPE

At minimum, the per-action trace must contain three explicit points:

Point 1 — Local refusal boundary

- actor
- boundary identifier
- invariant identity
- invariant evaluation result
- refusal capability state
- timestamp or equivalent ordering marker

Point 2 — System-wide refusal boundary

- actor
- boundary identifier
- invariant identity
- invariant evaluation result
- refusal capability state
- timestamp or equivalent ordering marker

Point 3 — True irreversible mutation authority

- actor or execution primitive identifier
- boundary identifier
- whether mutation was still preventable immediately before this point
- whether the governing invariant was still live here
- final allow / deny / downgrade / unverifiable result
- timestamp or equivalent ordering marker

---

7. WHY THE TRACE IS REQUIRED

Without this trace, BBIS can collapse into self-certification.

A system could otherwise say:

- authorization happened
- attestation exists
- execution integrity was claimed
- a secure gateway was present
- a signed record was produced

without proving where the governing invariant remained live and refusal-capable across the actual mutation-capable path.

The trace makes the claim diagnosable from outside.

---

8. PARTIAL CONFORMANCE RULE

A system may satisfy one boundary and fail another.

That must be classified honestly.

Examples:

- a system may have a valid local refusal boundary but lose system-wide refusal continuity under in-flight revocation
- a system may have strong earlier control but still fail at the true mutation authority if the actual irreversible primitive lies downstream and ungoverned
- a system may preserve earlier authorization but fail to prove execution-time continuity

These are not automatically strong or total fail.
They are partial unless the full requirement is satisfied.

---

9. REQUIRED FAILURE CLASSES

At minimum, this refinement requires explicit classification for:

- local-boundary-only conformance
- system-wide refusal collapse
- mutation-authority misidentification
- in-flight authority or delegation invalidation
- refusal-latency failure
- downstream uncontrolled path failure
- trace gap
- trace insufficiency
- stronger-claim scope inflation

No stronger continuity claim may survive once one of these failures is established for the claimed scope.

---

10. RELATION TO BBIS

This document does not redefine BBIS.

It refines how strong BBIS claims must be operationalized and tested.

BBIS remains the requirement that the same governing invariant survive across every mutation-capable boundary until the true irreversible primitive.

This refinement adds the rule that a system must identify and trace the three critical conformance boundaries if it wants to make that claim strongly and honestly.

---

11. FINAL RULE

A BBIS continuity claim is not mechanically serious unless the system can identify:

- the local refusal boundary
- the system-wide refusal boundary
- the true irreversible mutation authority

and produce a per-action trace showing:

- who held refusal capability at each boundary
- what governing invariant was evaluated there
- what the evaluation result was
- whether continuity survived to the true irreversible primitive for the claimed scope

If it cannot do that, the stronger continuity claim must not survive.
