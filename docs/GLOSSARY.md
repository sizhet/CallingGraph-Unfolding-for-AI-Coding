# GLOSSARY

## CallingGraph Unfolding for AI Coding

**Project:** CallingGraph Unfolding for AI Coding
**Short Name:** CGU — CallingGraph Unfolding
**Document:** Canonical Glossary
**Version:** v1.0
**Current Scope:** Function-Only CallingGraph

---

# 1. Purpose

This glossary defines the canonical terminology used throughout the CGU repository.

The purpose is to keep the meaning of key concepts stable across:

* theory;
* diagrams;
* AI coding architecture;
* validation;
* certification;
* future implementation.

CGU v1.0 deliberately restricts its formal scope to:

$$
\boxed{
F=Function
}
$$

Therefore, unless explicitly stated otherwise, all CallingGraph terms in this document refer to **Function-only CallingGraphs**.

---

# 2. CallingGraph

## Definition

A **CallingGraph** is a directed structural representation of callable functional units and their calling relationships.

Formally:

$$
CG=(V,E)
$$

where:

* \(V\) is the set of functional nodes;
* \(E\) is the set of directed calling edges.

For CGU v1.0:

$$
\boxed{
CG_F=(V_F,E_F)
}
$$

## Canonical Question

> What calls what?

## Scope Note

A CallingGraph does not necessarily encode:

* data values;
* conditions;
* runtime state;
* policy;
* timing;
* complete program semantics.

---

# 3. Functional Node

## Definition

A **Functional Node** is a callable computational unit represented as a node in the Function-only CallingGraph.

Examples may include:

```text
Function
Method
Service Operation
Callable Module Unit
```

Formally:

$$
v\in V_F
$$

## Canonical Meaning

A node represents a functional execution unit, not necessarily a source file or class.

---

# 4. Calling Edge

## Definition

A **Calling Edge** is a directed relation indicating that one functional unit may call another.

Formally:

$$
e=(v_i,v_j)\in E_F
$$

represented as:

$$
v_i\rightarrow v_j
$$

## Canonical Question

> Which functional unit can invoke which other functional unit?

---

# 5. Calling Path

## Definition

A **Calling Path** is an ordered sequence of functional nodes connected by calling edges.

Formally:

$$
P=(v_1,v_2,\dots,v_n)
$$

such that:

$$
(v_i,v_{i+1})\in E
$$

for the relevant adjacent pairs.

## Example

```text
Request
  ->
Validate
  ->
Authorize
  ->
Execute
  ->
Persist
```

## Role in CGU

Calling Paths may serve as units for:

* unfolding;
* validation;
* comparison;
* certification;
* future runtime trajectory analysis.

---

# 6. Folding

## Definition

**Folding** is the structural transformation of a richer program representation into a more compact structural representation.

In CGU:

$$
\boxed{
Program
\xrightarrow{Folding}
CallingGraph
}
$$

## Canonical Meaning

Folding preserves selected structural relations while suppressing implementation detail.

## Important Distinction

Folding is:

$$
Structural\ Compression
$$

not:

$$
File\ Compression
$$

or:

$$
Source\ Reconstruction
$$

---

# 7. CallingGraph Folding

## Definition

**CallingGraph Folding** is the specific process of extracting or constructing a CallingGraph from a program.

Formally:

$$
F_{CG}(Program)
=
CG
$$

## Output

The result is a folded functional representation of the implementation.

## Typical Use

CallingGraph Folding is used after coding to produce:

$$
RT\text{-}CG
$$

for comparison with the intended design.

---

# 8. Unfolding

## Definition

**Unfolding** is the selective expansion of a folded structural representation into a localized structural possibility space.

In CGU:

$$
\boxed{
U(CG,t)
}
$$

where:

* \(CG\) is the folded CallingGraph;
* \(t\) is a trigger;
* the result is a localized functional expansion.

## Core Principle

$$
\boxed{
Unfolding
\neq
Inverse(Folding)
}
$$

## Canonical Meaning

Unfolding does not reconstruct the original source program.

It exposes relevant functional possibilities encoded or implied by the structural representation.

---

# 9. CallingGraph Unfolding

## Definition

**CallingGraph Unfolding (CGU)** is the trigger-localized expansion of a CallingGraph into a bounded functional structural region or possibility space.

Formally:

$$
U:
(CG,t)
\rightarrow
\mathcal{U}
$$

with:

$$
\mathcal{U}_F(CG,t)
\subseteq
\mathcal{P}_F(CG)
$$

where \(\mathcal{P}_F(CG)\) denotes the broader functional possibility space associated with the graph.

## Canonical Statement

> **Fold Structure. Localize Relevance. Unfold Possibility.**

---

# 10. Trigger

## Definition

A **Trigger** is the structural input that determines what part of a CallingGraph should be localized and unfolded.

Formally:

$$
t\in T
$$

and:

$$
U(CG,t)
$$

produces the corresponding localized unfolding.

## Possible Trigger Types

```text
Function Trigger
Task Trigger
Path Trigger
Feature Trigger
Gap Trigger
Validation Trigger
```

## Role

The trigger prevents unnecessary full-graph expansion.

---

# 11. Trigger Set

## Definition

A **Trigger Set** is a collection of triggers used during unfolding or validation.

Formally:

$$
T=
\{t_1,t_2,\dots,t_n\}
$$

## Typical Use

For Differential Unfolding:

$$
U(DT\text{-}CG,T)
\leftrightarrow
U(RT\text{-}CG,T)
$$

---

# 12. Localization

## Definition

**Localization** is the process of identifying the structurally relevant region of a larger CallingGraph for a given trigger.

Conceptually:

$$
CG
\xrightarrow{Trigger}
CG_{local}
$$

## Canonical Transition

$$
\boxed{
Trigger
\rightarrow
Localization
\rightarrow
Unfolding
}
$$

## Purpose

Localization reduces the active reasoning or validation space.

---

# 13. Structural Hotspot

## Definition

A **Structural Hotspot** is a localized graph region considered relevant, critical, uncertain, or high-risk for the current task.

A hotspot may be identified by:

* trigger match;
* code change;
* high centrality;
* critical-path membership;
* past gap history;
* certification risk.

## Canonical Meaning

A hotspot is where deeper unfolding or inspection should occur.

---

# 14. Hotspot Unfolding

## Definition

**Hotspot Unfolding** is localized unfolding centered on a structurally important region.

Conceptually:

$$
StructuralHotspot
\rightarrow
LocalExpansion
$$

## Goal

Avoid treating the entire graph as equally relevant.

---

# 15. Localized Unfolding

## Definition

**Localized Unfolding** is unfolding restricted to a bounded structural region.

Formally:

$$
CG
\xrightarrow{t}
CG_{local}
\xrightarrow{U}
U_{local}
$$

## Importance

Localized Unfolding is the operational foundation for:

* task decomposition;
* context localization;
* repair;
* focused certification.

---

# 16. Bounded Unfolding

## Definition

**Bounded Unfolding** limits structural expansion by constraints such as:

* depth;
* source-target range;
* node count;
* path count;
* critical region.

Example:

$$
U(CG,t,d)
$$

where:

$$
d
$$

is the maximum unfolding depth.

## Important Limitation

$$
NoGapFound
$$

under bounded unfolding does not imply:

$$
NoGapExists
$$

outside the tested boundary.

---

# 17. Downstream Unfolding

## Definition

Expansion from a node toward functions it may call.

Formally:

$$
U_{\downarrow}(CG,v,d)
$$

## Question

> What functional structure can occur downstream from this node?

---

# 18. Upstream Unfolding

## Definition

Expansion toward possible callers or functional dependencies that lead into a target node.

Formally:

$$
U_{\uparrow}(CG,v,d)
$$

## Question

> What functional structure can reach this node?

---

# 19. Bidirectional Unfolding

## Definition

Unfolding both upstream and downstream around a structural hotspot.

Formally:

$$
U_{\leftrightarrow}(CG,v,d)
$$

## Use

Useful for local diagnosis and repair.

---

# 20. CallingGraph Unfolding Space

## Definition

The **CallingGraph Unfolding Space** is the set of functional structures exposed by unfolding under a given trigger or trigger set.

Formally:

$$
\boxed{
\mathcal{U}_F(CG,t)
}
$$

or:

$$
\mathcal{U}_F(CG,T)
$$

## Important Note

The Unfolding Space is generally a bounded or selected subset of all possible structural paths.

---

# 21. Full-Universe Search

## Definition

A search process that begins from the entire candidate universe.

Conceptually:

$$
Universe
\rightarrow
Target
$$

## CGU Context

Used as a baseline for understanding the evolution toward structural localization.

---

# 22. Two-Phase Search

## Definition

A search process that first narrows a large universe to a candidate space and then performs focused search.

Formally:

$$
Universe
\rightarrow
CandidateSpace
\rightarrow
Target
$$

## CGU Interpretation

Its deeper significance is structural localization.

---

# 23. Explicit Universe Localization

## Definition

Localization performed dynamically against a large search universe.

Conceptually:

$$
L(U,q)
\rightarrow
C
$$

where:

* \(U\) is the universe;
* \(q\) is the query or task;
* \(C\) is the candidate region.

## Relationship to CGU

CGU moves toward reusable pre-folded localization.

---

# 24. Pre-Folded Structural Localization

## Definition

Localization that reuses an already organized structural representation rather than rediscovering structure from the full universe.

Conceptually:

$$
FoldedStructure
\rightarrow
Hotspot
\rightarrow
Unfolding
$$

## Canonical Transition

$$
\boxed{
Explicit\ Universe\ Localization
\rightarrow
Pre\text{-}Folded\ Structural\ Localization
}
$$

---

# 25. Design-Time CallingGraph

## Definition

A **Design-Time CallingGraph (DT-CG)** is a CallingGraph defined before implementation is complete, representing the intended functional structure of future software.

Formally:

$$
\boxed{
DT\text{-}CG=(V_D,E_D)
}
$$

## Canonical Meaning

> **What the software should structurally become.**

## Role

DT-CG can support:

* structural design;
* wargaming;
* segmentation;
* dispatch;
* validation reference;
* certification.

---

# 26. Realized CallingGraph

## Definition

A **Realized CallingGraph** is the functional CallingGraph extracted from the actual implementation.

Also called:

$$
\boxed{
RT\text{-}CG
}
$$

within this repository.

## Canonical Meaning

> **What the software actually became.**

## Formation

$$
Program
\xrightarrow{Folding}
RT\text{-}CG
$$

---

# 27. Runtime CallingGraph

## Definition

Within CGU v1.0, **Runtime CallingGraph** is used as a practical synonym for Realized CallingGraph when referring to the graph representing implemented software.

## Scope Caution

RT-CG does not necessarily mean a graph reconstructed purely from runtime traces.

Unless otherwise stated:

$$
RT\text{-}CG
=
Realized\ CallingGraph
$$

not necessarily:

$$
ObservedDynamicTraceGraph
$$

This distinction should remain clear.

---

# 28. Structural Wargaming

## Definition

**Structural Wargaming** is the pre-coding exploration, comparison, and stress-testing of Design-Time CallingGraphs through unfolding and structural analysis.

Conceptually:

$$
DT\text{-}CG
\rightarrow
Unfold
\rightarrow
Simulate
\rightarrow
Revise
$$

## Questions

Structural Wargaming may ask:

* Is a functional path missing?
* Is the design over-coupled?
* Are critical functions reachable?
* Should an alternative plan be used?
* Can the graph be segmented effectively?

---

# 29. Pre-Coding Structural Simulation

## Definition

A more engineering-neutral term for Structural Wargaming.

It means exploring functional consequences of a DT-CG before code generation.

## Relationship

$$
StructuralWargaming
\approx
PreCodingStructuralSimulation
$$

within the CGU context.

---

# 30. Primary Plan

## Definition

The preferred Design-Time CallingGraph selected for execution.

Often written:

$$
DT\text{-}CG_A
$$

## Role

Represents the primary structural route for implementation.

---

# 31. Alternative Plan

## Definition

A competing Design-Time CallingGraph considered during Structural Wargaming.

Example:

$$
DT\text{-}CG_B
$$

## Use

Supports structural A/B comparison.

---

# 32. Fallback Plan

## Definition

A pre-designed alternative CallingGraph intended for use when the primary structure becomes infeasible or undesirable.

## Role

Supports:

$$
PlanFailure
\rightarrow
StructuralPlanSwitch
$$

---

# 33. Structural A/B Planning

## Definition

Comparison of two or more candidate Design-Time CallingGraphs before coding.

Conceptually:

$$
DT\text{-}CG_A
\leftrightarrow
DT\text{-}CG_B
$$

possibly including:

$$
U(DT_A,T)
\leftrightarrow
U(DT_B,T)
$$

## Goal

Compare structural alternatives before implementation cost is incurred.

---

# 34. Structural Segmentation

## Definition

Partitioning a CallingGraph into bounded functional subgraphs suitable for implementation or validation.

Formally:

$$
S(CG)
\rightarrow
\{G_1,G_2,\dots,G_n\}
$$

## Goal

Create manageable structural work units.

---

# 35. Structural Task Unit

## Definition

A bounded subgraph or functional region assigned as a coding or validation task.

Often represented as:

$$
G_i
$$

## Typical Contents

A Structural Task Unit may include:

* required nodes;
* required edges;
* interfaces;
* expected paths;
* local context.

---

# 36. Structural Dispatch

## Definition

The routing of a Structural Task Unit to an appropriate AI, agent, Brain Unit, or human specialist.

Formally:

$$
Dispatch(G_i)
\rightarrow
Agent_j
$$

## Canonical Principle

$$
\boxed{
Structure
\rightarrow
Organization
\rightarrow
Agents
}
$$

---

# 37. Localized AI Coding

## Definition

AI coding performed within a structurally bounded region derived from the CallingGraph.

Conceptually:

$$
G_i
+
Context_i
\rightarrow
Agent_i
\rightarrow
Code_i
$$

## Difference from Generic Context Reduction

Localized AI Coding is based on functional topology, not merely shorter text context.

---

# 38. Structural Context

## Definition

The context selected for an AI coding task based on the relevant CallingGraph region.

It may include:

* source files;
* adjacent functions;
* interfaces;
* tests;
* documentation;
* design constraints.

## Construction

$$
CG_i
\rightarrow
Context_i
$$

---

# 39. Bounded Autonomy

## Definition

The principle that an AI coding unit may exercise implementation freedom within structural constraints.

## Example

DT-CG requires:

$$
A\rightarrow B\rightarrow C
$$

The coding agent may choose implementation details while preserving the required structure.

## Canonical Meaning

$$
ImplementationFreedom
$$

inside:

$$
StructuralBoundary
$$

---

# 40. Structural Contract

## Definition

An explicit structural expectation governing a functional region or boundary.

Examples:

$$
A\rightarrow B
$$

must exist.

Or:

$$
Controller
\not\rightarrow
Database
$$

must hold.

## Role

Structural Contracts support:

* implementation coordination;
* validation;
* show-stop rules;
* certification.

---

# 41. Structural Control Plane

## Definition

The **Structural Control Plane** is the layer that organizes AI coding through structural design, localization, segmentation, routing, validation, and decision logic.

Within CGU:

$$
\boxed{
CallingGraph
\rightarrow
AI\ Coding\ Structural\ Control\ Plane
}
$$

## Responsibilities

May include:

* DT-CG management;
* unfolding;
* task dispatch;
* structural boundaries;
* comparison;
* repair routing;
* certification decisions.

---

# 42. Execution Plane

## Definition

The **Execution Plane** performs implementation work directed or bounded by the control plane.

Typical operations include:

* reasoning;
* code generation;
* local testing;
* implementation;
* repair.

## Relationship

$$
ControlPlane
\rightarrow
ExecutionPlane
$$

The control plane organizes; the execution plane acts.

---

# 43. AI Coding Control Plane

## Definition

The CGU-specific application of a Structural Control Plane to AI-assisted or autonomous coding.

It connects:

$$
Design
$$

$$
Dispatch
$$

$$
Generation
$$

$$
Validation
$$

$$
Certification
$$

$$
Learning
$$

## Canonical Statement

> **Move AI Coding control upstream—from Token Generation to Structural Planning.**

---

# 44. Structural Provenance

## Definition

**Structural Provenance** is the traceable chain connecting intent, planned structure, assigned work, generated code, realized structure, and validation evidence.

Canonical chain:

$$
\boxed{
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Task
\rightarrow
Agent
\rightarrow
Code
\rightarrow
RT\text{-}CG
\rightarrow
Evidence
}
$$

## Purpose

Supports auditability and explanation.

---

# 45. Structural Provenance Chain

## Definition

The explicit end-to-end record of Structural Provenance.

A richer version may include:

$$
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Unfolding
\rightarrow
Task
\rightarrow
Agent
\rightarrow
Code
\rightarrow
RT\text{-}CG
\rightarrow
DifferentialEvidence
\rightarrow
Certificate
$$

---

# 46. Structural Delta

## Definition

The static difference between two CallingGraphs.

For design vs realization:

$$
\boxed{
\Delta CG
=
DT\text{-}CG
\ominus
RT\text{-}CG
}
$$

## Possible Components

* missing nodes;
* unexpected nodes;
* missing edges;
* unexpected edges;
* broken paths;
* changed reachability.

---

# 47. Structural Difference Operator

## Definition

The symbol:

$$
\ominus
$$

is used in CGU as a conceptual structural difference operator.

## Scope Note

In v1.0 it is not yet a fully formalized algebraic operator.

Its precise implementation may depend on:

* nodes;
* edges;
* paths;
* subgraphs;
* unfolding results.

---

# 48. Unfolding Gap

## Definition

The **Unfolding Gap** is the structural difference between localized unfoldings of two CallingGraphs under comparable triggers.

For trigger \(t\):

$$
\boxed{
\Delta_U(t)
=
U(CG_A,t)
\ominus
U(CG_B,t)
}
$$

For Design-Time and Realized graphs:

$$
\boxed{
\Delta_U(t)
=
U(DT\text{-}CG,t)
\ominus
U(RT\text{-}CG,t)
}
$$

## Canonical Statement

> **What looks the same when folded may differ when unfolded.**

---

# 49. Missing Unfolding

## Definition

Functional structure expected from the design unfolding but absent from the realized unfolding.

Formally:

$$
\Delta_U^-
=
U_D-U_R
$$

## Examples

* missing node;
* missing edge;
* missing path;
* missing reachable region.

---

# 50. Unexpected Unfolding

## Definition

Functional structure appearing in the realized unfolding but absent from the design unfolding.

Formally:

$$
\Delta_U^+
=
U_R-U_D
$$

## Interpretation

May represent:

* defect;
* implementation detail;
* beneficial refinement;
* unauthorized dependency.

It requires interpretation rather than automatic rejection.

---

# 51. Reachability Gap

## Definition

A structural difference in whether one functional node can reach another.

Example:

$$
Reachable_D(A,C)
=
True
$$

but:

$$
Reachable_R(A,C)
=
False
$$

## Importance

Node-set equality does not imply reachability equivalence.

---

# 52. Path Gap

## Definition

A difference between expected and realized Calling Paths.

For path sets:

$$
P_D
$$

and:

$$
P_R
$$

missing paths are:

$$
P_D-P_R
$$

and unexpected paths are:

$$
P_R-P_D
$$

---

# 53. Granularity Gap

## Definition

A structural difference that becomes visible only at a finer graph resolution.

A coarse graph may show:

$$
CG_A^{(g_1)}
=
CG_B^{(g_1)}
$$

while a finer representation shows:

$$
CG_A^{(g_2)}
\neq
CG_B^{(g_2)}
$$

## Principle

$$
\boxed{
Graph\ Equivalence
\ Is\ Granularity\text{-}Dependent
}
$$

---

# 54. Structural Aliasing

## Definition

The phenomenon in which different richer program structures map to the same or similar folded CallingGraph representation.

Conceptually:

$$
F(X)
=
F(Y)
$$

while:

$$
X\neq Y
$$

## Significance

Structural Aliasing is one reason static CG match cannot automatically establish total equivalence.

---

# 55. Differential Unfolding

## Definition

**Differential Unfolding** is the paired unfolding and comparison of two CallingGraphs under comparable triggers.

Formally:

$$
U(CG_A,t)
\leftrightarrow
U(CG_B,t)
$$

followed by:

$$
\Delta_U(t)
$$

## For Certification

Most commonly:

$$
U(DT\text{-}CG,T)
\leftrightarrow
U(RT\text{-}CG,T)
$$

---

# 56. Differential CallingGraph Validation

## Definition

Static structural comparison between intended and realized CallingGraphs.

Typically includes:

$$
\Delta CG
$$

before Differential Unfolding is performed.

## Role

Forms a lower-cost first validation layer.

---

# 57. Unfolding Equivalence

## Definition

A relation indicating that two CallingGraphs produce equivalent unfolding results under a defined trigger set and unfolding rule.

For tested triggers:

$$
U(CG_A,T)
=
U(CG_B,T)
$$

## Important Scope Note

Tested Unfolding Equivalence does not necessarily mean universal equivalence.

---

# 58. Open-Unfolding Problem

## Definition

The **Open-Unfolding Problem** is the difficulty of proving complete unfolding equivalence when the relevant trigger or structural possibility space is not fully enumerable.

Even if:

$$
\forall t\in T_{tested},
\quad
\Delta_U(t)=0
$$

there may exist:

$$
t^*
\notin T_{tested}
$$

such that:

$$
\Delta_U(t^*)\neq0
$$

## Canonical Principle

$$
\boxed{
Finite\ Unfolding\ Evidence
\neq
Universal\ Unfolding\ Proof
}
$$

in the general case.

---

# 59. Static CallingGraph Match

## Definition

A degree of structural agreement between two CallingGraphs based on folded graph properties.

Possible comparison dimensions include:

* nodes;
* edges;
* paths;
* reachability;
* graph summaries.

## Important Principle

$$
\boxed{
CallingGraph\ Match
\neq
Runtime\ Equivalence
}
$$

---

# 60. Runtime Equivalence

## Definition

A stronger claim that two implementations behave equivalently under the relevant runtime semantics.

## CGU Scope Note

CGU v1.0 does not claim that Function-only CallingGraph equivalence establishes Runtime Equivalence.

Runtime Equivalence requires evidence beyond the Function-only CG model.

---

# 61. Runtime Evidence

## Definition

Observed evidence produced from actual program execution.

Examples include:

* unit tests;
* integration tests;
* execution traces;
* scenario runs;
* runtime calling traces.

Represented conceptually as:

$$
E_R
$$

## Role

Supplements structural evidence.

---

# 62. Runtime Trajectory

## Definition

An observed sequence of runtime functional execution events.

Conceptually:

$$
T_R
=
(v_1,v_2,\dots,v_n)
$$

with actual execution ordering.

## Scope Note

Runtime Trajectory is related to Calling Paths but is not identical to the static graph possibility space.

---

# 63. Certification

## Definition

In CGU, **Certification** is the process of evaluating structural and runtime evidence to support an assurance judgment.

It should not automatically mean universal proof.

## Canonical Model

$$
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
$$

---

# 64. Evidence-Bounded Certification

## Definition

A certification claim explicitly bounded by the evidence collected and the tested structural scope.

Canonical form:

$$
\boxed{
Certification
=
Claim
+
Evidence
+
Coverage
+
ResidualUncertainty
}
$$

## Purpose

Avoid overclaiming from incomplete evidence.

---

# 65. Certification Confidence

## Definition

The degree of assurance supported by the available certification evidence.

Represented as:

$$
C_{cert}
$$

Conceptually:

$$
C_{cert}
=
f(
CGMatch,
UnfoldingEvidence,
Coverage,
RuntimeEvidence,
ResidualRisk
)
$$

## Important Note

Certification Confidence is not automatically a calibrated probability of absolute correctness.

---

# 66. Certification Ladder

## Definition

The CGU evidence-depth hierarchy:

### C0

Syntax / Compilation

### C1

Static CallingGraph Match

### C2

Differential Structural Validation

### C3

Differential Unfolding + Coverage

### C4

Runtime Trajectory Validation

### C5

Integrated Evidence-Bounded Confidence

## Important Principle

The ladder measures:

$$
\boxed{
Assurance\ Evidence\ Depth
}
$$

not intrinsic software correctness.

---

# 67. Coverage

## Definition

The extent of structural or runtime space examined during validation.

Coverage may include:

$$
Coverage_T
$$

trigger coverage,

$$
Coverage_V
$$

node coverage,

$$
Coverage_E
$$

edge coverage,

$$
Coverage_P
$$

path coverage,

and:

$$
Coverage_D
$$

depth coverage.

---

# 68. Trigger Coverage

## Definition

The fraction of planned or relevant triggers actually tested.

If the planned trigger set is known:

$$
Coverage_T
=
\frac{|T_{tested}|}{|T_{planned}|}
$$

---

# 69. Node Coverage

## Definition

The fraction of intended graph nodes included in tested unfolding or validation regions.

$$
Coverage_V
=
\frac{|V_{covered}|}{|V_{DT}|}
$$

---

# 70. Edge Coverage

## Definition

The fraction of intended calling edges included in tested structural regions.

$$
Coverage_E
=
\frac{|E_{covered}|}{|E_{DT}|}
$$

---

# 71. Path Coverage

## Definition

The amount of planned or selected path space examined.

Because path space may be very large, Path Coverage is usually defined relative to a bounded or critical path set.

---

# 72. Depth Coverage

## Definition

The depth to which an unfolding region has been explored.

For example:

$$
d=3
$$

indicates that structural expansion was bounded to three levels under the selected rule.

---

# 73. Risk-Weighted Coverage

## Definition

Coverage weighted by structural criticality rather than treating all graph elements equally.

Conceptually:

$$
Coverage_{risk}
=
\frac{
\sum_{x\in Tested}Criticality(x)
}{
\sum_{x\in Planned}Criticality(x)
}
$$

## Purpose

Prioritize important functional regions.

---

# 74. Criticality

## Definition

The structural importance or potential impact of a node, edge, path, or gap.

Conceptually:

$$
Criticality(x)
$$

may depend on:

* functional role;
* reachability;
* security relevance;
* failure impact;
* boundary position.

---

# 75. Gap Severity

## Definition

The seriousness of a detected structural gap.

Conceptually:

$$
Severity(\Delta)
=
f(
Size,
Criticality,
Reachability,
Impact
)
$$

## Important Distinction

$$
GapSize
\neq
GapSeverity
$$

A small gap may be highly critical.

---

# 76. Structural Show-Stop

## Definition

A structural violation severe enough to block acceptance or require escalation regardless of aggregate similarity.

Examples:

```text
Missing Authorization Call
Broken Critical Path
Forbidden Direct Database Call
Required Service Unreachable
```

Formally:

$$
ShowStop(\Delta)
\in
\{True,False\}
$$

---

# 77. Approved Deviation

## Definition

A realized structural difference that has been reviewed and accepted as legitimate.

## Important Principle

Not every:

$$
\Delta CG
$$

or:

$$
\Delta_U
$$

is a defect.

An approved deviation may lead to:

$$
DT\text{-}CG'
$$

rather than code rollback.

---

# 78. Residual Risk

## Definition

Uncertainty remaining after the current certification process.

Examples include:

* untested triggers;
* bounded unfolding depth;
* unresolved unexpected paths;
* incomplete runtime scenarios;
* extraction uncertainty.

## Role

Residual Risk should be included in evidence-bounded certification.

---

# 79. Certification Record

## Definition

A structured artifact containing the evidence supporting a certification decision.

Typical contents include:

```text
DT-CG
RT-CG
Delta-CG
Trigger Set
Delta-U
Coverage
Runtime Evidence
Critical Gaps
Approved Deviations
Residual Risk
Certification Level
Decision
```

---

# 80. Evidence Package

## Definition

A broader term for the collection of inspectable artifacts supporting certification.

## Canonical Principle

$$
\boxed{
Certificate
=
Inspectable\ Evidence\ Package
}
$$

rather than only:

```text
PASS
```

or an opaque numerical score.

---

# 81. Incremental Certification

## Definition

Certification performed on a localized changed region rather than automatically revalidating the entire system.

Conceptually:

$$
ChangedCode
\rightarrow
ChangedCGRegion
\rightarrow
AffectedTriggers
\rightarrow
LocalizedReCertification
$$

---

# 82. Local Certification

## Definition

Certification applied to a bounded subgraph:

$$
Cert(G_i)
$$

before or during system integration.

---

# 83. Global Certification

## Definition

Certification applied to the integrated CallingGraph or software system.

## Important Principle

$$
LocalCertification
\not\Rightarrow
GlobalCertification
$$

because cross-boundary gaps may appear only after integration.

---

# 84. Boundary Evidence

## Definition

Evidence specifically validating structural relationships between subgraphs or coding units.

Examples include:

* expected cross-module calls;
* forbidden bypasses;
* interface path preservation.

---

# 85. Structural Repair

## Definition

Repair targeted at a localized structural deviation.

Conceptually:

$$
Gap
\rightarrow
Localization
\rightarrow
RepairTask
$$

## Goal

Avoid unnecessary large-scale regeneration.

---

# 86. Gap-Driven Repair

## Definition

A specific Structural Repair process in which:

$$
\Delta CG
$$

or:

$$
\Delta_U
$$

becomes the trigger for a repair task.

---

# 87. Replanning

## Definition

Revision of the Design-Time CallingGraph when the implementation or new evidence suggests the original design should change.

Conceptually:

$$
Evidence
\rightarrow
DesignReview
\rightarrow
DT\text{-}CG'
$$

## Distinction

Repair changes the implementation toward the current design.

Replanning changes the design itself.

---

# 88. Structural Convergence

## Definition

The iterative process of reducing unacceptable structural differences between Design-Time and Realized CallingGraphs.

Conceptually:

$$
RT_1
\rightarrow
Repair
\rightarrow
RT_2
\rightarrow
\dots
$$

until the realization enters an acceptable structural region.

---

# 89. Acceptable Structural Region

## Definition

A set of realized structures considered acceptable relative to a DT-CG.

Represented conceptually as:

$$
\mathcal{A}(DT)
$$

Acceptance occurs when:

$$
RT
\in
\mathcal{A}(DT)
$$

## Importance

The goal need not be exact graph identity.

---

# 90. Structural Learning

## Definition

Learning that modifies persistent structural representations based on repeated evidence.

Conceptually:

$$
Experience
\rightarrow
Difference
\rightarrow
Candidate
\rightarrow
Validation
\rightarrow
StructuralUpdate
$$

---

# 91. Structural Learning Signal

## Definition

A recurring structural difference that may justify updating future Design-Time CallingGraphs.

Examples:

* repeated missing node;
* repeated approved helper path;
* recurring boundary structure.

---

# 92. Candidate Structure

## Definition

A proposed new node, edge, path, or subgraph derived from recurring evidence but not yet promoted into the canonical structural design.

---

# 93. Structural Promotion

## Definition

The process of accepting a validated Candidate Structure into persistent design knowledge.

Conceptually:

$$
Candidate
\rightarrow
A/BValidation
\rightarrow
Promotion
$$

---

# 94. Structural Decay

## Definition

The weakening or removal of structural knowledge that becomes obsolete, unsupported, or repeatedly rejected.

## Future Role

Useful for long-term adaptive DT-CG libraries.

---

# 95. Dispatch-Tree Growth

## Definition

Structural evolution in which new task or functional branches become persistent routing branches for future AI dispatch.

Conceptually:

$$
ConsistencyFailure
\rightarrow
CandidateDifference
\rightarrow
A/B
\rightarrow
Branch
$$

## Role

Connects CGU with structural continual learning.

---

# 96. Structural Memory

## Definition

Persistent storage of validated functional structures, patterns, or DT-CGs for future reuse.

Possible contents include:

```text
Authentication Pattern
Persistence Pattern
Retry Pattern
Recovery Pattern
Audit Pattern
```

---

# 97. Structural Template

## Definition

A reusable functional structural pattern that guides new design without uniquely specifying implementation.

## Important Distinction

A Structural Template is not a rigid source-code template.

It defines:

$$
StructuralConstraint
+
ImplementationFreedom
$$

---

# 98. Generative Structural Skeleton

## Definition

A structure that constrains and guides future program generation without uniquely determining the final code.

Within CGU:

$$
\boxed{
DT\text{-}CG
=
Generative\ Structural\ Skeleton
}
$$

## Canonical Statement

> **A CallingGraph is not only a folded representation of existing software; it can also serve as a generative structural skeleton for future software.**

---

# 99. Structural Continuity

## Definition

The use of a shared structural representation across multiple lifecycle stages.

Conceptually:

$$
Design
\rightarrow
Execution
\rightarrow
Validation
$$

all remain connected through CallingGraph structure.

---

# 100. Structure-Centered Coding

## Definition

An AI coding paradigm in which structural planning organizes code generation.

Conceptual transition:

$$
\boxed{
Prompt\text{-}Centered\ Coding
\rightarrow
Structure\text{-}Centered\ Coding
}
$$

## Key Idea

Token generation remains an execution capability rather than the sole control center.

---

# 101. Structural Campaign Planning

## Definition

The use of Design-Time CallingGraphs, Structural Wargaming, alternative plans, segmentation, and dispatch to organize a larger AI coding effort.

## Canonical Statement

> **Design-Time CallingGraph moves AI coding control from token generation toward structural campaign planning.**

---

# 102. AI Coding Campaign

## Definition

A coordinated AI coding lifecycle organized around a Design-Time CallingGraph.

Canonical stages:

```text
Intent
Design
Wargaming
Planning
Dispatch
Execution
After-Action Review
Learning
```

## CGU Form

$$
Design
\rightarrow
Unfold
\rightarrow
Dispatch
\rightarrow
Code
\rightarrow
Fold
\rightarrow
Certify
\rightarrow
Learn
$$

---

# 103. After-Action Review

## Definition

Post-execution structural analysis comparing:

* intended structure;
* realized structure;
* runtime evidence;
* certification results.

## Purpose

Generate lessons for repair and future structural learning.

---

# 104. Structural Blackboard

## Definition

A shared structural coordination surface based on the DT-CG where AI units may observe:

* assigned regions;
* dependencies;
* progress;
* unresolved gaps;
* integration boundaries.

## Scope Note

This is an architectural interpretation, not a formal graph primitive in v1.0.

---

# 105. Execution Evidence

## Definition

Evidence returned by a coding or execution unit together with its generated code.

Possible fields:

```text
Task Unit
Expected CG
Realized CG
Changed Nodes
Changed Edges
Tests
Unresolved Gaps
Confidence
```

## Principle

$$
\boxed{
Code
+
ExecutionEvidence
}
$$

is preferable to code alone for autonomous coding systems.

---

# 106. Structural Explainability

## Definition

Explanation of AI coding decisions using explicit structural relationships and provenance.

Examples:

* why a region was selected;
* why an agent was dispatched;
* why certification confidence fell;
* why a structural deviation was rejected.

---

# 107. Structural Governance

## Definition

The use of explicit structural constraints, evidence, routing, and certification decisions to govern AI coding behavior.

Conceptual progression:

$$
CallingGraphAnalysis
\rightarrow
CallingGraphControl
\rightarrow
StructuralGovernance
$$

## Scope Note

Formal governance mechanisms are future work.

---

# 108. Certifiability

## Definition

The degree to which a software structure supports clear, efficient, and reliable validation.

Potential contributing factors include:

* explicit boundaries;
* low hidden coupling;
* clear critical paths;
* predictable call structure.

## Future Research Role

May become a design objective for AI-native software architecture.

---

# 109. Dispatchability

## Definition

The degree to which a software structure can be decomposed into clear task units and routed to specialized AI agents.

Potential properties include:

* functional cohesion;
* low boundary complexity;
* clear interfaces;
* bounded local context.

---

# 110. Repair Locality

## Definition

The degree to which a structural defect can be corrected within a small localized region.

Ideal property:

$$
SmallGap
\rightarrow
SmallRepairRegion
$$

rather than:

$$
SmallGap
\rightarrow
SystemWideRewrite
$$

---

# 111. Function Dimension

## Definition

The core structural dimension used in CGU v1.0.

Symbol:

$$
F
$$

Question:

> What calls what?

This is the only formal Core Dimension in the current version.

---

# 112. Condition / Context Dimension

## Definition

A proposed future structural dimension:

$$
C
$$

Question:

> Under what condition or context is this functional relation active?

## Scope

Future research only.

Not part of CGU v1.0 formal claims.

---

# 113. Runtime State Dimension

## Definition

A proposed future structural dimension:

$$
S
$$

Question:

> From which runtime state is this functional path available, and to which state does it lead?

## Scope

Future research only.

---

# 114. Policy / Projection Operator

## Definition

A proposed future operator that selects a structural view according to a policy or operating mode.

Represented as:

$$
\Pi_p
$$

Example:

$$
\Pi_{safe}(\mathcal{G})
\rightarrow
CG_{safe}
$$

## Important Distinction

Policy is not automatically treated as another ordinary graph dimension.

A future architecture may treat it as a projection or selection operator.

---

# 115. Projection

## Definition

A future operation selecting a relevant structural view from a richer structural space.

Conceptually:

$$
\Pi(\mathcal{G})
\rightarrow
CG_{local}
$$

## Difference from Unfolding

Projection asks:

> Which structural view is relevant?

Unfolding asks:

> How does that selected structure expand?

Thus:

$$
\boxed{
Projection
\rightarrow
Unfolding
}
$$

---

# 116. Calling Structural Space

## Definition

A proposed richer future structural object from which conventional CallingGraphs may be projected.

Represented conceptually as:

$$
\mathcal{G}
$$

## Future Question

> **Is a CallingGraph the complete object, or a functional projection of a richer Calling Structural Space?**

## Scope

Outside CGU v1.0.

---

# 117. Structural Runtime Path

## Definition

A proposed future richer path representation incorporating multiple structural dimensions.

Conceptually:

$$
P^*
=
\{(v_i,c_i,s_i,e_i)\}
$$

where functional units, conditions, states, and transitions may be represented together.

## Scope

Future work.

---

# 118. Structural Differential Algebra

## Definition

A possible future formal algebra for combining, comparing, projecting, and differencing structural objects.

Possible operators may include:

$$
\oplus
$$

structural merge,

$$
\ominus
$$

structural difference,

$$
\cap
$$

structural intersection,

and:

$$
\Pi
$$

projection.

## Scope

Not formally defined in CGU v1.0.

---

# 119. Extraction Uncertainty

## Definition

Uncertainty arising because the extracted RT-CG may not perfectly represent the real implementation structure.

Causes may include:

* dynamic dispatch;
* reflection;
* generated calls;
* framework callbacks;
* incomplete analysis.

## Importance

Future certification should distinguish:

$$
StructuralDifference
$$

from:

$$
ExtractionUncertainty
$$

---

# 120. Evidence Confidence

## Definition

Confidence in the reliability of the evidence source itself.

For example:

```text
Structural Match: High
Extraction Confidence: Medium
Runtime Coverage: High
```

## Distinction

$$
Confidence_{evidence}
$$

is different from:

$$
Confidence_{software}
$$

---

# 121. AI-Native Structural Software Design

## Definition

A future software design paradigm that considers not only runtime and human engineering qualities, but also:

* AI decomposability;
* dispatchability;
* structural localization;
* repair locality;
* certifiability.

## Scope

Long-term research direction.

---

# 122. CGU v1.0

## Definition

The first formal version of the CallingGraph Unfolding research framework.

Its scope is:

$$
\boxed{
Function\text{-}Only
}
$$

and centers on:

* Folding;
* Unfolding;
* DT-CG;
* RT-CG;
* \(\Delta CG\);
* \(\Delta_U\);
* Differential Unfolding;
* certification;
* control-plane architecture.

---

# 123. CGU

## Definition

**CGU** is the project abbreviation for:

$$
\boxed{
CallingGraph\ Unfolding
}
$$

within the repository:

**CallingGraph Unfolding for AI Coding**

The project studies how CallingGraph structure can evolve from a passive post-hoc representation into an active structural object supporting:

$$
Design
$$

$$
Localization
$$

$$
Dispatch
$$

$$
Generation
$$

$$
Validation
$$

$$
Certification
$$

$$
Learning
$$

---

# 124. Canonical Concept Chain

The main CGU terminology should be read as one connected chain:

```text
PROGRAM
   |
   | Folding
   v
CALLINGGRAPH
   |
   | Trigger
   v
LOCALIZATION
   |
   | Unfolding
   v
LOCAL FUNCTIONAL POSSIBILITY
```

Then:

```text
INTENT
   |
   v
DESIGN-TIME CG
   |
   v
STRUCTURAL WARGAMING
   |
   v
SEGMENTATION
   |
   v
DISPATCH
   |
   v
AI CODING
```

Then:

```text
PROGRAM
   |
   v
REALIZED CG
   |
   +--> Delta-CG
   |
   +--> Differential Unfolding
             |
             v
          Delta-U
             |
             v
        Runtime Evidence
             |
             v
         Certification
```

Then:

```text
Certification
      |
      v
Accept / Repair / Replan
      |
      v
Structural Learning
      |
      v
Better DT-CG
```

---

# 125. Canonical Equations

## CallingGraph

$$
\boxed{
CG_F=(V_F,E_F)
}
$$

## Folding

$$
\boxed{
Program
\xrightarrow{Folding}
CG
}
$$

## Unfolding

$$
\boxed{
U(CG,t)
}
$$

## Design-Time CallingGraph

$$
\boxed{
Intent
\rightarrow
DT\text{-}CG
}
$$

## Realized CallingGraph

$$
\boxed{
Program
\xrightarrow{Folding}
RT\text{-}CG
}
$$

## Structural Delta

$$
\boxed{
\Delta CG
=
DT\text{-}CG
\ominus
RT\text{-}CG
}
$$

## Unfolding Gap

$$
\boxed{
\Delta_U(t)
=
U(DT\text{-}CG,t)
\ominus
U(RT\text{-}CG,t)
}
$$

## Certification

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

## Control Loop

$$
\boxed{
DT\text{-}CG
\xrightarrow{Unfold}
LocalStructure
\xrightarrow{Dispatch}
AI\ Coding
\xrightarrow{Fold}
RT\text{-}CG
\xrightarrow{Diff}
Evidence
\xrightarrow{Certify}
Decision
\xrightarrow{Learn}
DT\text{-}CG'
}
$$

---

# 126. Canonical Statements

> **A CallingGraph is not only a folded representation of existing software; it can also serve as a generative structural skeleton for future software.**

> **Unfolding is not the inverse of Folding.**

> **Trigger-Localized Unfolding expands only the structurally relevant region.**

> **Design-Time CallingGraph describes what the future software should structurally become.**

> **Structure should determine organization, and organization should determine agent dispatch.**

> **CallingGraph similarity does not imply Unfolding equivalence.**

> **What looks the same when folded may differ when unfolded.**

> **CallingGraph match is structural evidence, not universal proof.**

> **Certification should be bounded by the evidence actually collected.**

> **Certify the evidence, not just the similarity.**

> **Move AI Coding control upstream—from Token Generation to Structural Planning.**

---

# 127. Terminology Discipline

For CGU v1.0, use:

$$
\boxed{
CallingGraph
}
$$

for Function-only node-edge calling structure.

Use:

$$
\boxed{
DT\text{-}CG
}
$$

for intended pre-coding CallingGraph structure.

Use:

$$
\boxed{
RT\text{-}CG
}
$$

for the realized CallingGraph extracted from implementation.

Use:

$$
\boxed{
\Delta CG
}
$$

for static graph difference.

Use:

$$
\boxed{
\Delta_U
}
$$

for unfolding difference.

Use:

$$
\boxed{
Differential\ Unfolding
}
$$

for paired unfolding and comparison.

Use:

$$
\boxed{
Certification\ Confidence
}
$$

for evidence-supported assurance, not automatic probability of absolute correctness.

---

# 128. Terms to Use Carefully

The following terms should not be used casually in CGU v1.0:

### Tensor

Do not call a richer CallingGraph a tensor unless actual tensor mathematics is defined.

### Quantum

Do not use quantum terminology merely as analogy for multiple structural dimensions.

### Complete Behavioral Equivalence

Do not claim this from Function-only graph matching.

### Universal Proof

Do not use unless the verification regime genuinely supports formal exhaustive proof.

### Runtime CallingGraph

Clarify whether this means Realized CG or dynamically observed runtime graph.

### Probability of Correctness

Do not equate Certification Confidence with calibrated probability unless such calibration has been established.

---

# 129. Scope Boundary

CGU v1.0 formally includes:

```text
Function Nodes
Calling Edges
Calling Paths
Folding
Unfolding
Localization
DT-CG
RT-CG
Delta-CG
Delta-U
Differential Unfolding
Structural Certification
AI Coding Control Plane
```

CGU v1.0 does **not** yet formally include:

```text
Condition Semantics
Runtime State Semantics
Policy Semantics
Data Semantics
Temporal Semantics
Probability
Complete Behavioral Equivalence
Calling Structural Space
```

These belong to future research.

---

# 130. Final Glossary Principle

The terminology of CGU should preserve one central distinction:

$$
\boxed{
Structure
\neq
Complete\ Semantics
}
$$

but structure can still become:

$$
\boxed{
Operational\ Infrastructure
}
$$

for:

$$
Design
$$

$$
Unfolding
$$

$$
Dispatch
$$

$$
Validation
$$

$$
Certification
$$

and:

$$
Learning
$$

---

**CGU — CallingGraph Unfolding**

> **Fold Structure. Localize Relevance. Unfold Possibility.**

> **Design the Structure Before Generating the Code.**

> **What Looks the Same When Folded May Differ When Unfolded.**

> **Certify the Evidence, Not Just the Similarity.**

> **Design. Unfold. Dispatch. Generate. Fold. Compare. Certify. Learn.**
