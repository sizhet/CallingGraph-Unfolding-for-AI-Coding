# CGU-005 — Differential Unfolding and Confidence-Based AI Coding Certification

## From Static CallingGraph Match to Evidence-Bounded Structural Assurance

**Project:** CallingGraph Unfolding for AI Coding
**Series:** CGU — CallingGraph Unfolding
**Document:** CGU-005
**Status:** Core Certification Framework
**Scope:** Function-Only CallingGraph
**Version:** v1.0

---

## Abstract

CallingGraph-based validation can provide strong structural evidence for AI-generated software, but static graph similarity alone is insufficient for complete assurance.

CGU-004 introduced the **Unfolding Gap**:

$$
\Delta_U
$$

and established the principle:

$$
CG\ Match
\neq
Unfolding\ Equivalence
\neq
Runtime\ Equivalence
$$

This paper develops the certification consequences of that result.

We introduce **Differential Unfolding Certification**, a layered validation process that compares a Design-Time CallingGraph and a Realized CallingGraph not only at the static graph level, but also through paired localized unfolding under a controlled trigger set.

The core evidence chain is:

$$
\boxed{
DT\text{-}CG
\leftrightarrow
RT\text{-}CG
\rightarrow
\Delta CG
\rightarrow
\Delta_U
\rightarrow
Coverage
\rightarrow
RuntimeEvidence
\rightarrow
CertificationConfidence
}
$$

The resulting certification is not generally a Boolean proof of universal equivalence.

Instead, it is an **evidence-bounded confidence judgment** whose strength depends on the amount, quality, coverage, and criticality of the structural and runtime evidence collected.

This paper proposes a certification ladder, a canonical evidence model, structural show-stopper rules, coverage reporting, and an explainable certification record.

The goal is not to weaken certification.

It is to make certification claims more precise, inspectable, and appropriate for large-scale AI/ASI coding systems.

---

# 1. Introduction

AI-generated software requires validation.

A generated program may:

* compile;
* pass tests;
* resemble the requested architecture;
* preserve many intended CallingGraph relations;

and still contain important structural differences.

The previous CGU papers introduced three increasingly powerful ideas:

$$
CallingGraph
$$

as folded functional structure,

$$
Design\text{-}Time\ CallingGraph
$$

as intended pre-coding structure,

and:

$$
Unfolding\ Gap
$$

as hidden divergence exposed by localized structural expansion.

These concepts naturally lead to a certification question:

> **How should CallingGraph evidence be converted into a defensible AI coding certification judgment?**

This paper proposes:

$$
\boxed{
Confidence\text{-}Based\ Structural\ Certification
}
$$

---

# 2. Why Static Certification Is Not Enough

A simple certification method might compare:

$$
DT\text{-}CG
$$

with:

$$
RT\text{-}CG
$$

and declare success if:

$$
Similarity(DT,RT)\geq\theta
$$

for some threshold \(\theta\).

This is useful but incomplete.

As shown in CGU-004:

$$
\Delta CG=0
$$

does not necessarily imply:

$$
\Delta_U=0
$$

and even:

$$
\Delta_U(T)=0
$$

for a finite trigger set does not generally establish universal runtime equivalence.

Therefore certification should integrate multiple evidence layers.

---

# 3. Certification as an Evidence Problem

The central question is not merely:

$$
Correct?
$$

but:

$$
\boxed{
What evidence supports the claim of correctness?
}
$$

A structural certification system should therefore collect evidence such as:

* compilation success;
* static CallingGraph agreement;
* differential graph results;
* differential unfolding results;
* trigger coverage;
* critical-path coverage;
* runtime test evidence;
* unresolved gaps;
* approved deviations.

Certification becomes an evidence aggregation problem.

---

# 4. The Design-Time Reference

The certification process begins with:

$$
DT\text{-}CG
$$

which records intended functional structure.

This provides a pre-implementation reference.

Without a design-time structure, validation must infer intent after implementation.

With a DT-CG:

$$
Intent
\rightarrow
DT\text{-}CG
$$

is preserved before code generation.

This makes later comparison more meaningful.

---

# 5. The Realized Structure

After implementation:

$$
Program
\xrightarrow{Folding}
RT\text{-}CG
$$

The realized graph represents:

> **What the software structurally became.**

Thus the primary comparison is:

$$
DT\text{-}CG
\leftrightarrow
RT\text{-}CG
$$

---

# 6. Static Differential CallingGraph

Define:

$$
\boxed{
\Delta CG = DT\text{-}CG
\ominus
RT\text{-}CG
}
$$

The static difference may include:

$$
\Delta V^-
$$

missing nodes,

$$
\Delta V^+
$$

unexpected nodes,

$$
\Delta E^-
$$

missing edges,

and:

$$
\Delta E^+
$$

unexpected edges.

This forms the first major structural evidence layer.

---

# 7. Static Match Categories

A static comparison can classify differences into:

```text id="j7z97v"
Required Node Missing
Required Edge Missing
Unexpected Node
Unexpected Edge
Forbidden Edge Present
Expected Path Broken
Unexpected Dependency
Approved Structural Deviation
```

This produces more useful evidence than a single similarity percentage.

---

# 8. Differential Unfolding

Static comparison is followed by:

$$
\boxed{
Differential\ Unfolding
}
$$

For each trigger:

$$
t_i
$$

the certification system computes:

$$
U_D(t_i) = U(DT\text{-}CG,t_i)
$$

and:

$$
U_R(t_i) = U(RT\text{-}CG,t_i)
$$

then compares them:

$$
\Delta_U(t_i) = U_D(t_i)
\ominus
U_R(t_i)
$$

---

# 9. Trigger Set

Let:

$$
T = \{t_1,t_2,\dots,t_n\}
$$

represent the certification trigger set.

Triggers may be selected from:

* critical functions;
* entry points;
* exit points;
* security-sensitive functions;
* persistence functions;
* recently modified functions;
* design-time hotspots;
* previous gap locations;
* high-centrality nodes.

The trigger set defines the tested Unfolding surface.

---

# 10. Differential Unfolding Certification

We define **Differential Unfolding Certification** as:

> **A certification process that compares intended and realized CallingGraphs through paired localized unfolding under a documented trigger set and incorporates the resulting structural differences into an assurance judgment.**

Formally:

$$
\boxed{
Cert_U = Compare(
U(DT\text{-}CG,T),
U(RT\text{-}CG,T)
)
}
$$

The output is not only:

$$
Pass/Fail
$$

but a structured evidence record.

---

# 11. Unfolding Difference Components

For each trigger:

$$
t_i
$$

the system may record:

$$
\Delta V_i
$$

$$
\Delta E_i
$$

$$
\Delta P_i
$$

representing node, edge, and path differences.

Thus:

$$
\Delta_U(t_i) = (
\Delta V_i,
\Delta E_i,
\Delta P_i
)
$$

in a simple Function-only implementation.

---

# 12. Missing and Unexpected Unfoldings

We distinguish:

$$
\Delta_U^-
$$

for expected structure missing from the realization,

and:

$$
\Delta_U^+
$$

for unexpected structure appearing in the realization.

Thus:

$$
\Delta_U = (
\Delta_U^-,
\Delta_U^+
)
$$

This distinction is important because the interpretation differs.

---

# 13. Missing Structure

A missing unfolding may indicate:

* omitted function;
* broken route;
* missing validation;
* missing logging;
* missing persistence;
* incomplete integration.

These often reduce confidence.

---

# 14. Unexpected Structure

Unexpected structure may indicate:

* beneficial implementation refinement;
* helper function;
* hidden dependency;
* architectural drift;
* unauthorized route;
* accidental complexity.

Unexpected structure should therefore be reviewed rather than automatically rejected.

---

# 15. Approved Deviations

Certification must allow justified structural deviation.

Suppose:

$$
RT\text{-}CG
$$

contains an additional helper function not present in:

$$
DT\text{-}CG
$$

but human or policy review determines that the change is beneficial.

Then the gap can be classified as:

$$
ApprovedDeviation
$$

rather than:

$$
Failure
$$

This keeps certification compatible with adaptive engineering.

---

# 16. Structural Show-Stoppers

Some findings should override aggregate confidence scores.

Examples include:

* missing required authentication;
* missing authorization path;
* forbidden direct database call;
* broken transaction path;
* unreachable required service;
* removal of required audit function.

We define:

$$
\boxed{
ShowStop(\Delta)
\in
\{True,False\}
}
$$

If:

$$
ShowStop=True
$$

the certification may be rejected regardless of average similarity.

---

# 17. Why Aggregate Similarity Is Insufficient

Suppose:

$$
Similarity=99.8\%
$$

but the remaining:

$$
0.2\%
$$

contains a missing authorization path.

Then:

$$
High\ Similarity
$$

does not imply:

$$
Acceptable\ Assurance
$$

Therefore certification must be:

$$
Criticality\text{-}Aware
$$

not only:

$$
Difference\text{-}Count\text{-}Aware
$$

---

# 18. Criticality

Let:

$$
Criticality(x)
$$

represent the importance of node, edge, or path \(x\).

A future severity function may be:

$$
Severity(\Delta) = f(
Criticality,
Reachability,
Location,
Impact
)
$$

The exact form depends on domain.

The key architectural principle is:

> **One critical gap may outweigh many ordinary matches.**

---

# 19. Coverage

Certification evidence is meaningful only when its scope is known.

Therefore every Differential Unfolding certification should report:

$$
\boxed{
Coverage
}
$$

Coverage describes how much of the intended structural space was actually tested.

---

# 20. Trigger Coverage

If a planned trigger set exists:

$$
T_{planned}
$$

and the tested set is:

$$
T_{tested}
$$

then:

$$
Coverage_T = \frac{|T_{tested}|}{|T_{planned}|}
$$

This is one simple coverage measure.

---

# 21. Node Coverage

Let:

$$
V_{covered}
$$

represent nodes appearing within tested unfolding regions.

Then:

$$
Coverage_V = \frac{|V_{covered}|}{|V_{DT}|}
$$

may provide node-level structural coverage.

---

# 22. Edge Coverage

Similarly:

$$
Coverage_E = \frac{|E_{covered}|}{|E_{DT}|}
$$

measures the fraction of design-time edges included in tested regions.

---

# 23. Path Coverage

Path coverage may be more difficult because the path space can be very large.

A bounded certification system may use:

* critical paths;
* selected paths;
* source-target path families;
* bounded-depth paths.

Then:

$$
Coverage_P
$$

can be reported relative to the chosen path set.

---

# 24. Depth Coverage

An unfolding process should also report depth.

If:

$$
d=2
$$

then certification should not imply that deeper structure was examined.

Thus:

$$
Coverage_D
$$

may record the maximum or effective unfolding depth.

---

# 25. Coverage Is Not Confidence

Coverage contributes to confidence.

But:

$$
Coverage
\neq
Confidence
$$

High coverage with many severe gaps should produce low confidence.

Low coverage with zero gaps should not produce high confidence.

Thus both quantity and quality of evidence matter.

---

# 26. The Open-Unfolding Boundary

CGU-004 introduced the Open-Unfolding Problem.

Even if:

$$
\Delta_U(T_{tested})=0
$$

there may exist:

$$
t^*
\notin
T_{tested}
$$

such that:

$$
\Delta_U(t^*)\neq0
$$

Therefore certification must preserve its evidence boundary.

---

# 27. Evidence-Bounded Certification

We define:

> **Evidence-Bounded Certification** as a certification claim whose scope and confidence are explicitly bounded by the structural and runtime evidence actually collected.**

Thus:

$$
\boxed{
Certification = Claim
+
Evidence
+
Coverage
+
Residual\ Uncertainty
}
$$

This is more precise than a bare binary label.

---

# 28. Certification Confidence

We define:

$$
\boxed{
C_{cert}
}
$$

as the confidence supported by available certification evidence.

Conceptually:

$$
C_{cert} = f(
E_{static},
E_{unfold},
E_{coverage},
E_{runtime},
E_{criticality}
)
$$

This is not yet a universal probability formula.

It is an architectural model for evidence aggregation.

---

# 29. A Minimal Confidence Form

A simplified conceptual formulation is:

$$
\boxed{
C_{cert} = f(
CGMatch,
UnfoldingMatch,
Coverage,
RuntimeEvidence,
ResidualRisk
)
}
$$

where:

* higher structural agreement increases confidence;
* higher tested coverage increases confidence;
* stronger runtime evidence increases confidence;
* unresolved critical gaps reduce confidence;
* unexplored regions preserve residual uncertainty.

---

# 30. Confidence Is Not Probability of Absolute Correctness

This distinction is essential.

A confidence score such as:

$$
0.92
$$

should not automatically be interpreted as:

> There is exactly a 92% probability that the software is universally correct.

Instead, it should mean something like:

> The collected structural and runtime evidence supports a high level of confidence under the defined certification scope.

This avoids false precision.

---

# 31. Certification Levels

A practical system may use levels rather than probabilities.

For example:

```text id="yq4ehg"
LOW
MODERATE
HIGH
VERY HIGH
```

or:

```text id="5pehq7"
C0
C1
C2
C3
C4
C5
```

The level should correspond to evidence depth.

---

# 32. The Certification Ladder

We propose the following ladder.

## C0 — Syntax / Compilation

Evidence:

* parse success;
* build success;
* basic type consistency.

This establishes only basic implementation validity.

---

## C1 — Static CallingGraph Match

Evidence:

$$
DT\text{-}CG
\leftrightarrow
RT\text{-}CG
$$

including node and edge comparison.

---

## C2 — Differential Structural Validation

Evidence includes:

$$
\Delta CG
$$

with:

* missing nodes;
* unexpected nodes;
* missing edges;
* unexpected edges;
* forbidden edges;
* critical static paths.

---

## C3 — Differential Unfolding Coverage

Evidence includes:

$$
\Delta_U(T)
$$

plus documented trigger and structural coverage.

---

## C4 — Runtime Trajectory Validation

Evidence includes runtime execution, tests, traces, or observed functional trajectories.

---

## C5 — Integrated Evidence-Bounded Confidence

Evidence combines:

$$
Static
+
Differential
+
Unfolding
+
Coverage
+
Runtime
+
Criticality
$$

into an explainable certification judgment.

---

# 33. The Ladder Is Not “Increasing Correctness”

This distinction matters.

C5 does not mean:

> The program is more correct than at C4.

It means:

> The certification claim is supported by more diverse and deeper evidence.

Thus the ladder measures:

$$
\boxed{
Assurance\ Evidence\ Depth
}
$$

not intrinsic software correctness.

---

# 34. Runtime Evidence

CallingGraph evidence should eventually be supplemented by runtime evidence.

Examples include:

* unit tests;
* integration tests;
* trace comparison;
* scenario execution;
* runtime calling traces;
* failure-path testing;
* regression tests.

Let:

$$
E_R
$$

represent runtime evidence.

Then:

$$
C_{cert} = f(
E_{CG},
E_U,
E_R
)
$$

where:

$$
E_{CG}
$$

is static graph evidence and:

$$
E_U
$$

is unfolding evidence.

---

# 35. Static, Unfolding, and Runtime Layers

The evidence hierarchy can be represented as:

```text id="q63rx0"
STATIC STRUCTURE
      |
      v
DIFFERENTIAL CG
      |
      v
DIFFERENTIAL UNFOLDING
      |
      v
RUNTIME TRAJECTORY
      |
      v
CERTIFICATION CONFIDENCE
```

Each layer answers a stronger question.

---

# 36. Static Layer Question

Static CG asks:

> Does the realized folded structure resemble the intended folded structure?

---

# 37. Unfolding Layer Question

Differential Unfolding asks:

> When comparable structural hotspots are activated, do intended and realized structures expand compatibly?

---

# 38. Runtime Layer Question

Runtime validation asks:

> Under actual execution scenarios, does the implemented software behave consistently with intended structural expectations?

These are related but not identical questions.

---

# 39. Certification Record

A useful certification system should produce an inspectable record.

For example:

```text id="x9lzg7"
Project:
Build:

Design-Time CG:
Realized CG:

Static CG Match:
Missing Nodes:
Unexpected Nodes:
Missing Edges:
Unexpected Edges:

Trigger Set:
Trigger Coverage:
Node Coverage:
Edge Coverage:
Depth Coverage:

Unfolding Gaps:
Critical Gaps:
Approved Deviations:

Runtime Tests:
Runtime Trace Evidence:

Residual Risks:

Certification Level:
Certification Confidence:
Decision:
```

This becomes a machine-readable and human-readable assurance artifact.

---

# 40. Certificate as Evidence Package

The final certificate should not merely contain:

```text id="8sokdt"
PASS
```

or:

```text id="tyeu9v"
Score: 94
```

Instead:

$$
\boxed{
Certificate = Evidence\ Package
}
$$

The certificate should preserve the reasoning surface that produced the judgment.

---

# 41. Structural Provenance

The certification record can also preserve provenance:

$$
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Unfolding
\rightarrow
AI\ Coding
\rightarrow
RT\text{-}CG
\rightarrow
Differential\ Unfolding
\rightarrow
RuntimeEvidence
\rightarrow
Certificate
$$

This makes AI coding more auditable.

---

# 42. From Post-Hoc Scoring to Lifecycle Assurance

Traditional certification often appears at the end:

$$
Code
\rightarrow
Score
$$

The CGU model integrates assurance throughout the lifecycle:

$$
Design
\rightarrow
Generation
\rightarrow
Validation
\rightarrow
Certification
$$

The Design-Time CallingGraph already creates the reference structure before coding begins.

This improves the meaning of later certification.

---

# 43. Certification Before Coding

Some assurance can even happen before code exists.

A DT-CG can be checked for:

* missing required function;
* forbidden relation;
* architectural violation;
* excessive coupling;
* broken expected path.

Thus:

$$
DT\text{-}CG
\rightarrow
Pre\text{-}Coding\ Structural\ Review
$$

becomes an early assurance stage.

---

# 44. Certification During Coding

During implementation, each local coding unit can return:

$$
Code_i
+
RT\text{-}CG_i
+
Evidence_i
$$

The control plane can compare:

$$
DT\text{-}CG_i
\leftrightarrow
RT\text{-}CG_i
$$

before integration.

This creates:

$$
\boxed{
Incremental\ Certification
}
$$

---

# 45. Certification After Coding

After integration:

$$
RT\text{-}CG_{global}
$$

is compared with:

$$
DT\text{-}CG_{global}
$$

and broader unfolding and runtime validation can occur.

Thus certification exists at multiple scales.

---

# 46. Local and Global Certification

A large project may support:

$$
Cert(G_i)
$$

for each local subgraph,

and:

$$
Cert(G)
$$

for the integrated system.

Local certificates can contribute evidence to global certification.

This supports scalable AI coding campaigns.

---

# 47. Certification Composition

Suppose:

$$
G = G_1
\cup
G_2
\cup
\dots
\cup
G_n
$$

A future certification architecture may combine:

$$
Cert(G_1),
Cert(G_2),
\dots,
Cert(G_n)
$$

plus cross-boundary evidence.

Importantly:

$$
Cert(G)
\neq
SimpleAverage(Cert(G_i))
$$

because interface and integration gaps may appear only globally.

---

# 48. Boundary Certification

Subgraph boundaries deserve special attention.

If:

$$
G_A
\rightarrow
G_B
$$

crosses an AI-agent or module boundary, certification should inspect that relation explicitly.

Boundary failures may include:

* missing interface call;
* wrong dependency direction;
* unexpected bypass;
* duplicated route.

Thus:

$$
BoundaryEvidence
$$

should be part of integrated assurance.

---

# 49. Critical-Path Certification

A practical certification strategy may prioritize critical paths.

Let:

$$
P_{critical}
\subseteq
P(DT\text{-}CG)
$$

Then:

$$
U(DT,P_{critical})
\leftrightarrow
U(RT,P_{critical})
$$

can receive higher certification priority.

This provides:

$$
Risk\text{-}Weighted\ Coverage
$$

rather than treating all paths equally.

---

# 50. Risk-Weighted Coverage

A simple conceptual model is:

$$
Coverage_{risk} = \frac{
\sum_{x\in Tested}Criticality(x)
}{
\sum_{x\in Planned}Criticality(x)
}
$$

This may be more meaningful than raw percentage coverage.

Again, the exact metric is application-specific.

---

# 51. Evidence Weighting

Different evidence layers may receive different weights:

$$
w_{CG}
$$

$$
w_U
$$

$$
w_R
$$

with:

$$
C = f(
w_{CG}E_{CG},
w_UE_U,
w_RE_R
)
$$

But weights should not be treated as arbitrary scoring decorations.

They should correspond to documented certification policy.

---

# 52. Policy Profiles

A future implementation may define profiles such as:

```text id="1cd7bv"
EXPERIMENTAL
STANDARD
STRICT
SAFETY-CRITICAL
```

Each profile could require different:

* trigger coverage;
* depth;
* runtime tests;
* show-stop rules;
* acceptable deviations.

Thus certification becomes profile-aware.

---

# 53. Confidence Thresholds

A policy may define:

$$
C_{cert}\geq\theta
$$

for acceptance.

But thresholding should occur only after show-stop checks.

Thus:

$$
if\ ShowStop=True
\Rightarrow
Reject
$$

even if:

$$
C_{cert}\geq\theta
$$

This prevents aggregate scores from hiding critical failures.

---

# 54. Human Escalation

Certification should support escalation.

For example:

$$
UnresolvedCriticalGap
\rightarrow
HumanReview
$$

or:

$$
UnexpectedHighImpactPath
\rightarrow
SpecialistReview
$$

This produces:

$$
\boxed{
Automatic\ Certification
+
Structured\ Human\ Escalation
}
$$

rather than attempting to automate every judgment.

---

# 55. Reviewable Evidence

A reviewer should be able to inspect:

* which triggers were tested;
* which paths differed;
* which gaps were accepted;
* which gaps were unresolved;
* what runtime tests were run;
* why confidence was assigned.

Explainability is therefore part of certification quality.

---

# 56. Confidence Accumulation

Certification confidence can increase as evidence accumulates.

For example:

$$
E_1
\rightarrow
C_1
$$

then:

$$
E_1+E_2
\rightarrow
C_2
$$

then:

$$
E_1+E_2+E_3
\rightarrow
C_3
$$

This produces an evidence accumulation process.

---

# 57. Confidence Can Also Decrease

New evidence may reveal a hidden gap.

Thus:

$$
C_{old}
$$

may decrease after:

$$
\Delta_U(t^*)\neq0
$$

This is expected.

Certification should remain revisable when new evidence appears.

---

# 58. Certificate Versioning

A useful system may therefore maintain:

```text id="targm2"
Certificate v1
Certificate v2
Certificate v3
```

with each version linked to:

* code version;
* DT-CG version;
* RT-CG version;
* trigger set;
* test evidence.

This supports reproducibility.

---

# 59. Certification and Continuous Development

Software evolves.

Therefore certification should not be treated as permanent.

A code change may alter:

$$
RT\text{-}CG
$$

and invalidate previous evidence.

A change-aware system can localize re-certification:

$$
ChangedCode
\rightarrow
ChangedCGRegion
\rightarrow
AffectedTriggers
\rightarrow
LocalizedRevalidation
$$

This is another benefit of structural localization.

---

# 60. Differential Re-Certification

Instead of re-certifying the entire system after every small change:

$$
\Delta Code
\rightarrow
\Delta CG
\rightarrow
Affected\ Unfoldings
\rightarrow
Focused\ Certification
$$

This could reduce cost for large systems.

---

# 61. Certification as a Feedback Signal

Certification results can also guide repair.

For example:

$$
LowConfidence
\rightarrow
InspectEvidence
\rightarrow
LocateGap
\rightarrow
GenerateRepairTask
$$

Thus certification participates in the coding loop rather than serving only as a final label.

---

# 62. Repair Loop

The loop becomes:

$$
Code
\rightarrow
RT\text{-}CG
\rightarrow
\Delta_U
\rightarrow
Repair
\rightarrow
Code'
$$

followed by:

$$
Revalidate
$$

This provides structurally targeted AI repair.

---

# 63. Certification and Structural Learning

Repeated certification evidence can reveal recurring patterns.

Suppose the same deviation repeatedly appears and is repeatedly approved.

Then:

$$
RepeatedApprovedGap
\rightarrow
CandidateDT\text{-}CGUpdate
$$

Thus certification can improve future design structures.

---

# 64. From Certificate to Learning

The complete feedback loop is:

$$
Certificate
\rightarrow
GapHistory
\rightarrow
PatternDiscovery
\rightarrow
DesignImprovement
\rightarrow
BetterDT\text{-}CG
$$

This connects assurance to structural continual learning.

---

# 65. Why This Matters for AI/ASI Coding

Large-scale AI coding may involve many agents and many generated modules.

Without structural certification, the system may become difficult to audit.

CallingGraph-based certification offers:

* explicit design reference;
* machine-readable structural evidence;
* localized validation;
* explainable differences;
* composable local evidence;
* runtime linkage;
* confidence tracking.

These properties may become increasingly important as coding autonomy increases.

---

# 66. Certification as a Control Mechanism

Certification is not only post-hoc evaluation.

It can influence:

* whether a subgraph is accepted;
* whether code is merged;
* whether an agent is re-run;
* whether a stronger model is invoked;
* whether human review is required;
* whether the DT-CG itself should be revised.

Thus:

$$
\boxed{
Certification
\rightarrow
Control
}
$$

---

# 67. The Certification Control Loop

A possible control loop is:

```text id="v3h6d9"
Generate
   |
   v
Fold
   |
   v
Compare
   |
   v
Unfold
   |
   v
Evaluate Evidence
   |
   +--> Accept
   |
   +--> Repair
   |
   +--> Escalate
   |
   +--> Replan
```

This makes certification an operational part of AI coding.

---

# 68. The Certification Object

The true certification object is therefore not only:

$$
RT\text{-}CG
$$

A richer object is:

$$
\boxed{
(
DT\text{-}CG,
RT\text{-}CG,
\Delta CG,
\Delta_U,
Coverage,
RuntimeEvidence
)
}
$$

This tuple provides the core evidence substrate.

---

# 69. Structural Provenance Chain

The complete provenance chain is:

$$
\boxed{
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Unfolding
\rightarrow
Generation
\rightarrow
RT\text{-}CG
\rightarrow
DifferentialUnfolding
\rightarrow
RuntimeValidation
\rightarrow
Certificate
}
$$

This chain records not only what code exists, but how it relates to intended structure.

---

# 70. A Canonical Confidence Model

A simple conceptual model is:

$$
\boxed{
C_{final} = f(
DesignEvidence,
CGMatch,
UnfoldingEvidence,
Coverage,
RuntimeEvidence,
ResidualRisk
)
}
$$

where:

$$
ResidualRisk
$$

represents unresolved uncertainty and uncovered structural regions.

This is intentionally general.

Future implementations may instantiate it differently.

---

# 71. Residual Risk

Even high-confidence certification should preserve residual risk.

Examples include:

* untested triggers;
* untested depth;
* unresolved unexpected paths;
* incomplete runtime scenarios;
* external dependency uncertainty.

Thus a certificate may state:

```text id="14mnq6"
Confidence: High
Residual Risk:
- Deep branch beyond unfolding depth not tested
- One unexpected helper path approved
- External service behavior excluded
```

This is more scientifically honest and operationally useful.

---

# 72. No Universal Boolean Claim by Default

The default CGU certification claim should not be:

$$
\boxed{
Correct=True
}
$$

unless the system and verification regime genuinely support such a proof.

Instead:

$$
\boxed{
Evidence\ Supports\ Confidence\ C
Within\ Scope\ S
}
$$

This wording preserves rigor.

---

# 73. Constrained Formal Systems

Some systems may admit stronger guarantees.

If all relevant functional structures are finite, fully modeled, and exhaustively checked, then:

$$
\Delta CG=0
$$

and:

$$
\Delta_U=0
$$

across the full defined space may support formal equivalence claims.

CGU does not deny this possibility.

It simply avoids assuming it by default.

---

# 74. Function-Only Scope

The present framework remains:

$$
\boxed{
F=Function\ Only
}
$$

The certification evidence concerns:

* functions;
* calling relations;
* calling paths;
* reachable functional regions.

It does not yet certify:

* condition semantics;
* runtime state;
* data correctness;
* temporal correctness;
* policy correctness.

This boundary must be explicit in every certificate.

---

# 75. Scope Statement Example

A certificate may include:

```text id="qogc0r"
Scope:
Function-only CallingGraph structural certification.

Included:
Nodes, calling edges, selected paths, localized unfolding.

Excluded:
State, data values, timing, policy semantics, full behavioral equivalence.
```

This prevents overclaiming.

---

# 76. Future Multi-Dimensional Certification

Future work may extend:

$$
F
$$

to:

$$
F+C
$$

then:

$$
F+C+S
$$

and richer projection or policy operators.

Then certification could compare:

$$
\Delta_U^{F}
$$

$$
\Delta_U^{C}
$$

$$
\Delta_U^{S}
$$

across multiple structural dimensions.

But this is deliberately deferred.

---

# 77. Research Questions

### RQ-1 — How should \(\Delta CG\) and \(\Delta_U\) be combined?

Possible approaches include:

* weighted scores;
* rule-based policies;
* critical-path-first logic;
* evidence graphs.

---

### RQ-2 — How should certification confidence be calibrated?

A confidence score should correspond to reproducible evidence, not arbitrary intuition.

---

### RQ-3 — How should trigger sets be generated?

Possible methods include:

* design-driven selection;
* code-change-driven selection;
* risk-driven selection;
* coverage-driven selection;
* historical-gap-driven selection.

---

### RQ-4 — What coverage measures are most informative?

Node, edge, path, depth, trigger, and risk-weighted coverage may differ significantly.

---

### RQ-5 — How should show-stoppers be defined?

Different domains require different criticality policies.

---

### RQ-6 — How should approved deviations affect certification?

A deviation may require:

* documentation;
* DT-CG update;
* human approval;
* revalidation.

---

### RQ-7 — How should local certificates compose globally?

Subgraph certification does not automatically imply system certification.

---

### RQ-8 — Can Differential Unfolding reduce false-positive certification?

This is a central empirical question.

---

### RQ-9 — Can CG-based certification improve autonomous repair?

The gap structure may provide precise repair targets.

---

### RQ-10 — Can certification evidence improve future DT-CGs?

This connects assurance to structural learning.

---

# 78. Canonical Certification Pipeline

```text id="97gry2"
                       INTENT
                         |
                         v
                  DESIGN-TIME CG
                         |
                         v
                      AI CODING
                         |
                         v
                     PROGRAM
                         |
                       FOLD
                         |
                         v
                    REALIZED CG
                         |
              +----------+----------+
              |                     |
              v                     v
          DELTA-CG              TRIGGER SET
                                      |
                                      v
                          DIFFERENTIAL UNFOLDING
                                      |
                                      v
                                   DELTA-U
                                      |
                                      v
                                  COVERAGE
                                      |
                                      v
                             RUNTIME EVIDENCE
                                      |
                                      v
                          CRITICALITY / POLICY
                                      |
                                      v
                         CERTIFICATION CONFIDENCE
```

---

# 79. Canonical Certification Record

A compact canonical record may be:

```text id="9zk5fq"
CGU CERTIFICATION RECORD

Design Reference:
- DT-CG Version

Realized Structure:
- RT-CG Version

Static Evidence:
- Node Match
- Edge Match
- Missing / Unexpected Structure
- Show-Stoppers

Unfolding Evidence:
- Trigger Set
- Delta-U
- Missing Paths
- Unexpected Paths

Coverage:
- Trigger Coverage
- Node Coverage
- Edge Coverage
- Path / Depth Coverage

Runtime Evidence:
- Tests
- Traces
- Scenarios

Residual Risk:
- Uncovered Regions
- Unresolved Gaps

Result:
- Certification Level
- Confidence
- Decision
- Review Requirements
```

---

# 80. Canonical Statements

### Canonical Statement I

> **AI coding certification should compare intended and realized CallingGraphs at both the folded and unfolded structural levels.**

### Canonical Statement II

> **Differential Unfolding converts CallingGraph Unfolding into a paired validation mechanism for detecting hidden local structural divergence.**

### Canonical Statement III

> **Certification confidence should reflect evidence quality, coverage, criticality, runtime validation, and residual uncertainty—not static similarity alone.**

### Canonical Statement IV

> **A high CallingGraph match is structural evidence, not universal proof of behavioral equivalence.**

### Canonical Statement V

> **A useful certificate is an inspectable evidence package, not merely a Boolean label or opaque score.**

---

# 81. The Certification Equation

The core architecture can be summarized as:

$$
\boxed{
\Delta CG
+
\Delta_U
+
Coverage
+
RuntimeEvidence
+
Criticality
\rightarrow
CertificationConfidence
}
$$

with:

$$
ShowStop=True
\Rightarrow
Reject/Escalate
$$

This is the canonical CGU certification model.

---

# 82. The Broader Transition

Traditional software certification often begins after implementation.

CGU introduces a lifecycle approach:

$$
\boxed{
Design
\rightarrow
Generate
\rightarrow
Fold
\rightarrow
Compare
\rightarrow
Unfold
\rightarrow
Validate
\rightarrow
Certify
}
$$

This makes structural assurance part of the entire AI coding process.

---

# 83. From Certification to Governance

Once certification results influence:

* acceptance;
* merge;
* repair;
* escalation;
* replanning;

the certification system becomes part of AI coding governance.

Thus:

$$
\boxed{
Structural\ Evidence
\rightarrow
Certification
\rightarrow
Control
}
$$

The final CGU paper develops this broader control-plane architecture.

---

# 84. Conclusion

CallingGraph certification should not stop at static graph comparison.

A Design-Time CallingGraph and a Realized CallingGraph may appear similar while exposing different functional structures under localized unfolding.

Therefore certification should compare:

$$
DT\text{-}CG
$$

and:

$$
RT\text{-}CG
$$

at multiple evidence levels.

The core structural evidence is:

$$
\Delta CG
$$

followed by:

$$
\Delta_U
$$

under a documented trigger set.

This evidence should be interpreted together with:

$$
Coverage
$$

$$
RuntimeEvidence
$$

$$
Criticality
$$

and:

$$
ResidualRisk
$$

The result is:

$$
\boxed{
Evidence\text{-}Bounded\ Certification\ Confidence
}
$$

rather than an unjustified assumption of universal Boolean equivalence.

The objective is not to make certification weaker.

It is to make certification more accurate about what has actually been demonstrated.

The final certification object is therefore not merely:

$$
PASS
$$

or:

$$
FAIL
$$

but an inspectable evidence package connecting:

$$
Intent
\rightarrow
Design
\rightarrow
Generation
\rightarrow
RealizedStructure
\rightarrow
Unfolding
\rightarrow
RuntimeEvidence
\rightarrow
Assurance
$$

This architecture is especially appropriate for future AI/ASI coding systems, where software may be generated by many specialized agents and where human reviewers need structural evidence rather than opaque confidence claims.

The resulting principle is:

$$
\boxed{
Certify the Evidence, Not Just the Similarity.
}
$$

---

## Next in the CGU Series

**CGU-006 — CallingGraph as an AI Coding Control Plane**

The final paper integrates the complete lifecycle:

$$
\boxed{
Design
\rightarrow
Unfold
\rightarrow
Simulate
\rightarrow
Dispatch
\rightarrow
Code
\rightarrow
Fold
\rightarrow
Compare
\rightarrow
Certify
\rightarrow
Learn
}
$$

and develops the CallingGraph as a structural control plane spanning:

* pre-coding design;
* structural wargaming;
* agent dispatch;
* localized generation;
* post-coding validation;
* certification;
* repair;
* and structural learning.

---

## Scope Note

CGU-005 remains strictly within the **Function-only CallingGraph model**.

The certification framework evaluates functional structural evidence only.

It does not claim complete certification of:

* runtime state;
* condition semantics;
* data values;
* timing;
* probability;
* policy correctness;
* total behavioral equivalence.

Future work may extend the same Differential Unfolding framework into richer Calling Structural Spaces.

---

**CGU-005 Principle**

$$
\boxed{
\text{Certify the Evidence, Not Just the Similarity.}
}
$$
