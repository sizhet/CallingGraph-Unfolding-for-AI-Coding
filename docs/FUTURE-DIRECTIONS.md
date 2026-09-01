# FUTURE DIRECTIONS

## CallingGraph Unfolding for AI Coding

**Project:** CallingGraph Unfolding for AI Coding
**Short Name:** CGU — CallingGraph Unfolding
**Document:** Future Research Directions
**Version:** v1.0
**Current Scope:** Function-Only CallingGraph

---

# 1. Purpose

CGU v1.0 deliberately begins with a narrow research object:

$$
\boxed{
F = Function
}
$$

The current repository studies whether a Function-only CallingGraph can already support:

* Folding;
* Unfolding;
* structural localization;
* Design-Time CallingGraphs;
* structural wargaming;
* AI coding segmentation;
* agent dispatch;
* DT-CG vs RT-CG comparison;
* Differential Unfolding;
* evidence-bounded certification;
* structural repair;
* structural learning.

This restricted scope is intentional.

The next research question is not:

> How many dimensions can be added to the CallingGraph?

The better question is:

> **Which additional structures are operationally necessary, and what new capability does each one provide?**

The future of CGU should therefore proceed by controlled structural expansion rather than unlimited graph enrichment.

---

# 2. The Immediate Priority: Build the Function-Only Runtime

Before adding richer dimensions, CGU should first prove that the Function-only model can operate as an executable system.

The minimum engineering loop is:

```text id="pjn2jt"
Design-Time CG
      |
      v
Trigger
      |
      v
Localization
      |
      v
Unfolding
      |
      v
Coding Task
      |
      v
Implementation
      |
      v
RT-CG Extraction
      |
      v
Delta-CG
      |
      v
Differential Unfolding
      |
      v
Delta-U
      |
      v
Certification Report
```

This should be the first experimental milestone.

---

# 3. CGU-MVP-001 — Design-Time CallingGraph

The first minimal demo should define a small DT-CG explicitly.

For example:

```text id="j00qye"
Request
   |
   v
Validate
   |
   v
Authorize
   |
   v
Execute
   |
   v
Persist
```

The demo should support:

* node definition;
* edge definition;
* entry points;
* critical paths;
* required edges;
* forbidden edges.

The objective is not sophisticated graph tooling.

The objective is to establish a stable Design-Time structural object.

---

# 4. CGU-MVP-002 — Trigger-Localized Unfolding

The second demo should implement:

$$
U(CG,t)
$$

for a Function-only graph.

Possible trigger types include:

```text id="nqwqys"
Node Trigger
Path Trigger
Feature Trigger
Gap Trigger
```

Minimal unfolding operators may include:

$$
U_{downstream}(CG,v,d)
$$

$$
U_{upstream}(CG,v,d)
$$

$$
U_{bidirectional}(CG,v,d)
$$

where:

$$
d
$$

is an unfolding-depth bound.

The goal is to demonstrate that:

$$
LargeGraph
\rightarrow
LocalizedSubgraph
$$

can become an explicit runtime operation.

---

# 5. CGU-MVP-003 — DT-CG vs RT-CG

The next demo should extract a Realized CallingGraph from a small program:

$$
Program
\xrightarrow{Folding}
RT\text{-}CG
$$

Then compare:

$$
DT\text{-}CG
\leftrightarrow
RT\text{-}CG
$$

and compute:

$$
\Delta CG
$$

The initial report can include:

```text id="q87bbj"
Missing Nodes
Unexpected Nodes
Missing Edges
Unexpected Edges
Broken Required Paths
Forbidden Edges
```

This establishes the static validation layer.

---

# 6. CGU-MVP-004 — Differential Unfolding

The fourth demo should apply the same trigger set:

$$
T = \{t_1,t_2,\dots,t_n\}
$$

to both:

$$
DT\text{-}CG
$$

and:

$$
RT\text{-}CG
$$

and compute:

$$
\boxed{
\Delta_U(T) = U(DT\text{-}CG,T)
\ominus
U(RT\text{-}CG,T)
}
$$

A minimal report may classify:

```text id="3chjvg"
Missing Unfolding
Unexpected Unfolding
Missing Path
Unexpected Path
Reachability Gap
Depth-Limited Gap
```

This would provide the first executable demonstration of the Unfolding Gap.

---

# 7. CGU-MVP-005 — Certification Report

The next step should combine evidence.

A minimal certificate could report:

```text id="uug0zd"
DT-CG Version
RT-CG Version

Delta-CG
Delta-U

Trigger Set
Coverage

Critical Gaps
Approved Deviations

Runtime Test Results

Certification Level
Residual Risk
Decision
```

The important objective is explainability.

The certificate should preserve evidence rather than output only a numerical score.

---

# 8. CGU-MVP-006 — Closed Repair Loop

Once a gap is detected:

$$
\Delta_U
$$

the system should create a localized repair task:

$$
\boxed{
Gap
\rightarrow
Localization
\rightarrow
Repair
}
$$

Then:

$$
Code'
\rightarrow
RT\text{-}CG'
$$

and certification can be repeated.

This closes the first real CGU runtime loop.

---

# 9. Research Direction I — Better Unfolding Operators

The current formulation:

$$
U(CG,t)
$$

is intentionally abstract.

Future work should define a practical family of unfolding operators.

Possible operators include:

### Downstream Unfolding

$$
U_{\downarrow}(CG,v,d)
$$

Expand functions reachable downstream from \(v\).

### Upstream Unfolding

$$
U_{\uparrow}(CG,v,d)
$$

Expand possible callers and dependency sources.

### Bidirectional Unfolding

$$
U_{\leftrightarrow}(CG,v,d)
$$

Expand both directions.

### Source-Target Unfolding

$$
U(CG,v_s,v_t)
$$

Find bounded structural regions connecting two functional points.

### Critical-Path Unfolding

Expand around predefined high-importance paths.

### Gap-Driven Unfolding

Use an observed difference as the next trigger.

The long-term goal is not one universal unfolding operator.

It is a small algebra of structural expansion operations.

---

# 10. Research Direction II — Adaptive Unfolding Depth

A fixed depth:

$$
d
$$

is simple but often inefficient.

A future system may use adaptive depth:

$$
d = f(
Criticality,
Complexity,
Uncertainty,
GapHistory
)
$$

For ordinary functions:

$$
d=1
$$

may be enough.

For critical regions:

$$
d=5
$$

may be justified.

Thus:

$$
\boxed{
Unfold\ Deeper\ Where\ Structural\ Risk\ Is\ Higher
}
$$

could become a practical policy.

---

# 11. Research Direction III — Hotspot Selection

Trigger selection is a central open problem.

A system should not unfold arbitrary regions equally.

Potential hotspot signals include:

* graph centrality;
* recent code changes;
* critical-path membership;
* security sensitivity;
* repeated past failures;
* low certification confidence;
* high fan-in;
* high fan-out;
* cross-module boundaries.

A future hotspot score could take the form:

$$
H(v) = f(
Centrality,
Criticality,
Change,
GapHistory,
BoundaryRole
)
$$

This could guide both validation and human review.

---

# 12. Research Direction IV — Structural Coverage

CGU-005 introduces several coverage ideas.

Future work should determine which measures are practically useful.

Possible measures include:

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

A stronger metric may be:

$$
Coverage_{risk}
$$

which weights coverage by structural importance.

The objective should be:

> Report not only what was tested, but how much structurally relevant space was examined.

---

# 13. Research Direction V — Better ΔCG and ΔU Metrics

Simple set difference is useful for an MVP.

But future systems may require richer comparison.

For:

$$
\Delta CG
$$

possible measures include:

* node difference;
* edge difference;
* direction difference;
* path difference;
* reachability difference;
* boundary difference;
* graph-edit distance.

For:

$$
\Delta_U
$$

possible measures include:

* missing local nodes;
* unexpected local nodes;
* missing paths;
* unexpected paths;
* local reachability change;
* unfolding-depth divergence.

The key challenge is to preserve interpretability.

A metric that produces only:

```text id="1dshd9"
Distance = 0.173
```

is less useful than one that also explains where the difference occurs.

---

# 14. Research Direction VI — Structural Criticality

Not all functional nodes are equally important.

Future CGU systems should distinguish:

$$
GapSize
$$

from:

$$
GapCriticality
$$

A single missing authorization edge may matter more than many harmless helper-function differences.

A future criticality model may consider:

$$
Criticality(x) = f(
Role,
Reachability,
Impact,
BoundaryPosition,
FailureCost
)
$$

This could support risk-weighted certification.

---

# 15. Research Direction VII — Structural Show-Stop Policies

Some deviations should immediately block acceptance.

Examples may include:

```text id="0ox7i8"
Missing Required Security Call
Forbidden Direct Persistence Call
Broken Critical Path
Required Function Unreachable
Bypass Around Validation
```

Future systems should support declarative structural show-stop rules.

For example:

$$
Rule:
Authorize
\rightarrow
Execute
$$

must hold.

Or:

$$
Controller
\not\rightarrow
Database
$$

must hold.

This could turn DT-CG into a lightweight structural policy language.

---

# 16. Research Direction VIII — Design-Time CG Generation

One of the largest future problems is:

$$
Requirement
\rightarrow
DT\text{-}CG
$$

How should this transformation occur?

Possible approaches include:

* human-authored DT-CG;
* LLM-generated DT-CG;
* template-based generation;
* retrieval from structural libraries;
* hybrid human-AI design;
* iterative A/B graph generation.

A practical workflow may be:

```text id="0ijqo3"
Requirement
   |
   v
Candidate DT-CGs
   |
   v
Structural Wargaming
   |
   v
Human / AI Review
   |
   v
Selected DT-CG
```

This could become one of the major research areas of CGU.

---

# 17. Research Direction IX — Structural Wargaming Algorithms

CGU-003 introduces Structural Wargaming.

Future research should make it computational.

Candidate analyses include:

* required path validation;
* unreachable-node detection;
* dependency cycles;
* cross-module coupling;
* fan-out risk;
* critical-path depth;
* alternative-plan comparison.

A candidate design score might be:

$$
Score(CG_D) = f(
Coverage,
Modularity,
Complexity,
Risk,
Cost
)
$$

But this should remain interpretable and domain-aware.

---

# 18. Research Direction X — Multiple Design Plans

Future systems may maintain:

$$
DT\text{-}CG_A
$$

$$
DT\text{-}CG_B
$$

$$
DT\text{-}CG_C
$$

for:

* primary;
* alternative;
* fallback;

plans.

The system can compare:

$$
U(DT_A,T)
$$

$$
U(DT_B,T)
$$

$$
U(DT_C,T)
$$

before coding.

This opens the possibility of:

$$
\boxed{
Structural\ Plan\ Search
}
$$

and:

$$
\boxed{
Structural\ Plan\ Switching
}
$$

during AI coding.

---

# 19. Research Direction XI — AI Coding Segmentation

A large DT-CG must be partitioned into coding units.

A future segmentation function may be:

$$
S(CG)
\rightarrow
\{G_1,G_2,\dots,G_n\}
$$

Possible criteria include:

* low cross-boundary coupling;
* functional cohesion;
* bounded complexity;
* clear interfaces;
* agent specialization;
* certification requirements.

The segmentation problem may become as important as code generation itself.

---

# 20. Research Direction XII — Agent Selection

Once:

$$
G_i
$$

is defined, which AI unit should implement it?

A future dispatch function may be:

$$
D(G_i)
\rightarrow
Agent_j
$$

based on:

* domain expertise;
* previous performance;
* coding language;
* complexity;
* risk;
* tool access;
* context size.

This supports the principle:

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

# 21. Research Direction XIII — Brain-Unit Specialization

A future AI coding system may contain specialized Brain Units.

For example:

```text id="8gugkl"
Security Brain Unit
Database Brain Unit
API Brain Unit
Testing Brain Unit
Architecture Brain Unit
```

DT-CG segmentation could provide the structural routing layer for such specialization.

Thus:

$$
FunctionalTopology
\rightarrow
CognitiveSpecialization
$$

becomes a research direction.

---

# 22. Research Direction XIV — Structural Context Construction

A localized subgraph does not directly define all prompt context.

A future system must convert:

$$
CG_i
$$

into:

$$
Context_i
$$

Possible context elements include:

* relevant source files;
* upstream functions;
* downstream functions;
* interfaces;
* tests;
* documentation;
* known gaps.

Thus:

$$
CG_i
\rightarrow
ContextBuilder
\rightarrow
LocalizedAIContext_i
$$

could become a major practical component.

---

# 23. Research Direction XV — Structural Provenance

CGU proposes the provenance chain:

$$
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
$$

Future systems should preserve this chain explicitly.

A structural provenance record could answer:

* Which requirement created this node?
* Which DT-CG region created this task?
* Which agent implemented this path?
* Which code corresponds to this edge?
* Which evidence certified this region?

This could significantly improve AI coding auditability.

---

# 24. Research Direction XVI — Evidence-Preserving Agents

Future coding agents should return more than source code.

A richer return package could include:

```text id="icmy98"
Task Unit
Expected CG Region
Generated Code
Realized CG Region
Changed Nodes
Changed Edges
Tests
Unresolved Gaps
Confidence
```

This creates:

$$
\boxed{
Code
+
ExecutionEvidence
}
$$

rather than code alone.

That evidence can feed directly into certification.

---

# 25. Research Direction XVII — Incremental Certification

Large projects should not require full recertification after every small change.

A better loop is:

$$
ChangedCode
\rightarrow
ChangedCGRegion
\rightarrow
AffectedTriggers
\rightarrow
LocalizedReCertification
$$

This could dramatically reduce validation cost.

The challenge is determining when local recertification is sufficient and when global validation is required.

---

# 26. Research Direction XVIII — Composable Certification

If:

$$
G
=
G_1\cup G_2\cup\dots\cup G_n
$$

can:

$$
Cert(G_i)
$$

contribute to:

$$
Cert(G)
$$

?

Probably yes, but not through simple averaging.

Cross-boundary relations must also be validated.

Therefore:

$$
GlobalCertification
=
LocalEvidence
+
BoundaryEvidence
+
IntegrationEvidence
$$

is a promising direction.

---

# 27. Research Direction XIX — Certification Calibration

CGU currently uses Certification Confidence as an architectural concept.

Future work should determine how confidence can be calibrated empirically.

A useful confidence model should satisfy:

* interpretability;
* reproducibility;
* evidence traceability;
* domain sensitivity;
* resistance to false precision.

The goal should not be a decorative score.

The goal should be:

$$
\boxed{
Evidence\ That\ Justifies\ Assurance
}
$$

---

# 28. Research Direction XX — Runtime Trajectory Integration

Function-only CallingGraphs capture static functional relations.

Runtime traces add observed execution order.

A future integration might be:

$$
RT\text{-}CG
+
RuntimeTrajectory
$$

Then certification can compare:

$$
ExpectedFunctionalPath
$$

with:

$$
ObservedRuntimePath
$$

This connects structural possibility to actual execution.

---

# 29. Research Direction XXI — Calling Paths as Runtime Units

A Calling Path:

$$
P
=
(v_1,v_2,\dots,v_n)
$$

may become an important unit for:

* testing;
* certification;
* runtime tracing;
* failure localization;
* structural learning.

Future work may treat paths as first-class objects rather than deriving them only during traversal.

This creates a bridge from static graph structure toward runtime trajectory intelligence.

---

# 30. Research Direction XXII — From Function to Condition

The first major structural extension beyond v1.0 may be:

$$
F
\rightarrow
F+C
$$

where:

$$
C
=
Condition / Context
$$

The question changes from:

> What calls what?

to:

> **Under what condition is a calling relation active?**

For example:

```text id="7xzxrz"
Payment
   |
   +-- success --> Persist
   |
   +-- failure --> Rollback
```

This would increase structural discrimination significantly.

But it should be introduced only after the Function-only runtime is stable.

---

# 31. Research Direction XXIII — Runtime State Dimension

The next extension may be:

$$
F+C
\rightarrow
F+C+S
$$

where:

$$
S
=
Runtime\ State
$$

Then the question becomes:

> From which state does this functional path become available, and to which state does it lead?

A possible path object becomes:

$$
P^*
=
\{
(v_i,c_i,s_i,e_i)
\}
$$

This begins to resemble a Structural Runtime Path.

---

# 32. Research Direction XXIV — Policy as Projection, Not Another Dimension

Policy should not automatically be added as another ordinary graph attribute.

A more useful future model may treat policy as an operator.

Let:

$$
\Pi_p
$$

be a policy projection.

Then:

$$
\Pi_p(\mathcal{G})
\rightarrow
CG_p
$$

could produce:

```text id="mu6596"
SAFE view
AGGRESSIVE view
TEST view
EMERGENCY view
```

The important conceptual distinction is:

### Projection

asks:

> Which structural region or view is relevant under this policy?

### Unfolding

asks:

> How can that selected structure expand?

Thus:

$$
\boxed{
Projection
\rightarrow
Unfolding
}
$$

may become a central future composition.

---

# 33. Research Direction XXV — Calling Structural Space

A deeper future question is whether a conventional CallingGraph is the full structural object.

Perhaps:

$$
CallingGraph
$$

is only one projection of a richer:

$$
\boxed{
Calling\ Structural\ Space
}
$$

Let:

$$
\mathcal{G}
$$

represent such a space.

Then:

$$
\Pi_{c,s,p,t}(\mathcal{G})
\rightarrow
G_{local}
$$

and:

$$
U(G_{local})
\rightarrow
StructuralTrajectory
$$

This would generalize CGU substantially.

---

# 34. Do Not Build a “Super CallingGraph”

A major methodological caution is necessary.

The future should not simply attach every possible attribute to nodes and edges.

That would create an increasingly complex:

```text id="8jfi40"
Super CallingGraph
```

with:

* function;
* condition;
* state;
* policy;
* data;
* time;
* probability;
* runtime history;
* confidence;
* environment;

all embedded indiscriminately.

This would likely become difficult to reason about and difficult to operate.

A better principle is:

$$
\boxed{
Do\ Not\ Enrich\ the\ Graph\ Indefinitely;
Enrich\ Its\ Coordinate\ System
}
$$

---

# 35. Multi-Dimensional Structural Views

A future representation might conceptually separate:

$$
CG_F
$$

functional relations,

$$
CG_C
$$

condition/context relations,

and:

$$
CG_S
$$

state relations.

Conceptually:

$$
\mathcal{G}
\sim
CG_F
\otimes
CG_C
\otimes
CG_S
$$

This notation is only suggestive.

It should **not** be called a tensor unless mathematically meaningful tensor operations are actually defined.

The important point is multiple composable structural views.

---

# 36. Research Direction XXVI — Projection + Unfolding

One of the most promising future formulations is:

$$
\boxed{
Trajectory
=
U(
\Pi_{c,s,p,t}(\mathcal{G})
)
}
$$

First:

$$
Projection
$$

selects the currently relevant structural view.

Then:

$$
Unfolding
$$

expands it.

This may provide a clean architecture for richer runtime intelligence.

---

# 37. Research Direction XXVII — High-Dimensional DT-CG

Today, alternative plans may be represented as:

$$
DT\text{-}CG_A
$$

$$
DT\text{-}CG_B
$$

$$
DT\text{-}CG_C
$$

A richer future model may encode several alternatives inside one structural space and project them according to operating mode.

For example:

$$
\Pi_{normal}(\mathcal{G})
$$

$$
\Pi_{failure}(\mathcal{G})
$$

$$
\Pi_{emergency}(\mathcal{G})
$$

This could reduce duplication among separate design graphs.

---

# 38. Research Direction XXVIII — Structural Runtime Paths

If Function, Condition, and State are eventually integrated, a Calling Path may evolve into a richer unit:

$$
P^*
=
(
Function,
Condition,
State,
Edge
)^*
$$

Such paths could support:

* runtime diagnosis;
* failure replay;
* certification;
* trajectory comparison;
* predictive planning.

This may become a bridge between CallingGraph research and broader runtime structural intelligence.

---

# 39. Research Direction XXIX — Structural Differential Algebra

Current CGU uses:

$$
\ominus
$$

informally as structural difference.

Future work may define a more precise algebra over:

* nodes;
* edges;
* paths;
* unfoldings;
* projections.

Possible operators might include:

$$
\oplus
$$

for structural merge,

$$
\ominus
$$

for structural difference,

$$
\cap
$$

for common structural region,

and:

$$
\Pi
$$

for projection.

A small Structural Differential Algebra could make the framework more rigorous.

---

# 40. Research Direction XXX — Unfolding Equivalence

Future work should define different levels of equivalence.

Possible hierarchy:

$$
NodeEquivalence
$$

$$
EdgeEquivalence
$$

$$
PathEquivalence
$$

$$
BoundedUnfoldingEquivalence
$$

$$
FullDefinedSpaceEquivalence
$$

This would clarify what exactly a certification claim proves.

---

# 41. Research Direction XXXI — Open-Unfolding Theory

CGU-004 introduces the Open-Unfolding Problem.

This deserves deeper formal study.

Questions include:

* When is complete trigger enumeration possible?
* When is bounded unfolding sufficient?
* Under what graph constraints can unfolding equivalence be proven?
* How should residual structural uncertainty be represented?
* Can probabilistic sampling give meaningful confidence bounds?

This could become a distinct theoretical branch of CGU.

---

# 42. Research Direction XXXII — Structural Learning from Gaps

Unfolding Gaps can become learning signals.

The basic loop is:

$$
RecurringGap
\rightarrow
CandidateDifference
\rightarrow
A/B
\rightarrow
Validation
\rightarrow
Promotion
$$

A future system could update:

$$
DT\text{-}CG
$$

automatically under controlled evidence.

This connects certification directly to structural continual learning.

---

# 43. Research Direction XXXIII — Structural Promotion and Decay

Not every observed structural difference should become permanent knowledge.

Future systems may need:

$$
Promotion
$$

and:

$$
Decay
$$

rules.

For example:

```text id="ab3jxk"
Repeated Successful Structure
   -> Promote

Rare / Obsolete Structure
   -> Decay

High-Risk Rejected Structure
   -> Suppress
```

This would make DT-CG libraries adaptive.

---

# 44. Research Direction XXXIV — Dispatch-Tree Growth

Repeated task classes may create new dispatch branches.

The learning cycle becomes:

```text id="44tyf1"
Consistency Failure
      |
      v
Candidate Difference
      |
      v
A/B Validation
      |
      v
New Structural Branch
      |
      v
New Specialist Dispatch
```

This is one path from ordinary AI coding to structural continual learning.

---

# 45. Research Direction XXXV — Structural Memory Libraries

Validated subgraphs may be stored as reusable structural knowledge.

A library might contain:

```text id="nhec78"
Authentication Pattern
Transaction Pattern
Retry Pattern
Audit Pattern
Persistence Pattern
Recovery Pattern
```

Then:

$$
NewRequirement
\rightarrow
StructuralRetrieval
\rightarrow
CandidateDT\text{-}CG
$$

This could reduce repeated design effort.

---

# 46. Research Direction XXXVI — Certification-Guided Structural Retrieval

Structural memory should not be ranked only by similarity.

A stronger retrieval signal could include prior certification evidence.

For example:

$$
Rank(Pattern)
=
f(
StructuralSimilarity,
PriorSuccess,
CertificationDepth,
GapHistory
)
$$

This would allow the system to prefer not only familiar structures, but well-validated structures.

---

# 47. Research Direction XXXVII — Human Review Localization

CGU may support more efficient human oversight.

Instead of reviewing everything:

$$
HumanReview
\rightarrow
CriticalHotspots
$$

Possible triggers for human review include:

* high \(\Delta_U\);
* unresolved show-stop;
* large design deviation;
* new structural pattern;
* low coverage;
* fallback-plan activation.

This could make Human+AI coding governance more scalable.

---

# 48. Research Direction XXXVIII — Structural Explainability

A CGU system should be able to explain:

```text id="zb4djq"
Why was this agent selected?

Why was this region unfolded?

Why was this deviation rejected?

Why was confidence reduced?

Why was replanning triggered?
```

The answer should be grounded in structural provenance.

This could become a strong form of explainability for autonomous coding systems.

---

# 49. Research Direction XXXIX — Structural Governance

Once CGU determines:

* allowed functional routes;
* forbidden dependencies;
* required paths;
* certification thresholds;
* escalation rules;

it begins to function as governance infrastructure.

This suggests a future progression:

$$
CallingGraphAnalysis
\rightarrow
CallingGraphControl
\rightarrow
CallingGraphGovernance
$$

This direction should be explored carefully and incrementally.

---

# 50. Research Direction XL — AI-Native Software Architecture

Future software architecture may be designed not only for:

* runtime performance;
* human readability;
* maintainability;

but also for:

* AI decomposability;
* structural localization;
* agent specialization;
* certification ease;
* repair locality.

This suggests:

$$
\boxed{
Structural\ AI\text{-}Native\ Software\ Design
}
$$

as a broader research field.

---

# 51. Research Direction XLI — Designing for Certifiability

Some architectures may be easier to certify than others.

For example:

* explicit functional boundaries;
* low hidden coupling;
* clear critical paths;
* limited bypasses;
* predictable call direction.

This suggests a new design objective:

$$
\boxed{
Certifiability
}
$$

Architecture could be evaluated partly by how easily its structural claims can be validated.

---

# 52. Research Direction XLII — Designing for Local Repair

Similarly, architectures may differ in repair locality.

A structure is easier to maintain if:

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

This suggests another potential architecture metric:

$$
RepairLocality
$$

which may become important for autonomous coding systems.

---

# 53. Research Direction XLIII — Designing for Dispatchability

A future AI-native architecture may also optimize:

$$
Dispatchability
$$

A highly dispatchable structure has:

* clear subgraphs;
* limited cross-boundary dependencies;
* identifiable task units;
* specialist-friendly regions.

This could improve multi-agent coding efficiency.

---

# 54. Research Direction XLIV — Experimental Benchmarks

CGU ultimately requires empirical testing.

A benchmark suite could compare:

### Baseline

```text id="vgca7p"
Requirement
   ->
LLM / Agents
   ->
Code
```

against:

### CGU

```text id="evx1ud"
Requirement
   ->
DT-CG
   ->
Unfolding
   ->
Dispatch
   ->
Code
   ->
RT-CG
   ->
Certification
```

Metrics may include:

* structural error rate;
* missing-path rate;
* repair cost;
* context size;
* agent coordination cost;
* certification coverage;
* time to convergence.

---

# 55. Research Direction XLV — Controlled A/B Experiments

A particularly useful experimental pattern would be:

$$
Baseline
\leftrightarrow
CGU
$$

using the same coding task.

Compare:

```text id="h0rlrd"
Code Quality
Structural Fidelity
Number of Repairs
Integration Failures
Context Cost
Human Review Time
```

This would test whether structural planning provides measurable advantage.

---

# 56. Research Direction XLVI — Failure Injection

Another useful experiment is structural failure injection.

For example deliberately remove:

* one critical node;
* one required edge;
* one fallback path.

Then measure whether:

* static \(\Delta CG\);
* Differential Unfolding;
* runtime validation;

detect the failure.

This would directly test the value of \(\Delta_U\).

---

# 57. Research Direction XLVII — Unfolding Gap Benchmarks

A dedicated benchmark could contain pairs of programs with:

$$
HighCGSimilarity
$$

but different local functional structure.

The goal would be to test:

$$
\boxed{
Can\ Differential\ Unfolding\ detect\ differences
that\ static\ comparison\ misses?
}
$$

This would be a particularly strong validation of CGU-004.

---

# 58. Research Direction XLVIII — Real Repository Experiments

After toy demos, CGU should move toward medium-sized real repositories.

Important challenges will include:

* indirect calls;
* reflection;
* framework callbacks;
* generated code;
* dependency injection;
* dynamic dispatch.

These are still Function-level problems and therefore belong naturally within the v1.x research path.

---

# 59. Research Direction XLIX — Extraction Uncertainty

Realized CallingGraphs are not always perfectly observable.

Therefore future certification should distinguish:

$$
StructuralDifference
$$

from:

$$
ExtractionUncertainty
$$

A missing edge may mean:

* the edge is absent;
* the extractor failed;
* the call is dynamic.

This uncertainty should be represented explicitly rather than silently treated as structural fact.

---

# 60. Research Direction L — Confidence in the Evidence Itself

Future certification may need two kinds of confidence:

$$
Confidence_{software}
$$

and:

$$
Confidence_{evidence}
$$

For example:

```text id="6lpfqx"
Structural Match: High
Extraction Confidence: Medium
Runtime Coverage: High
```

This prevents weak measurement from being mistaken for strong evidence.

---

# 61. A Proposed Research Roadmap

A practical progression could be:

```text id="vdiajs"
PHASE 1
Function-Only MVP

PHASE 2
Differential Unfolding Experiments

PHASE 3
Certification Runtime

PHASE 4
AI Coding Dispatch

PHASE 5
Structural Learning

PHASE 6
Condition / Context Extension

PHASE 7
Runtime State Extension

PHASE 8
Calling Structural Space
```

This preserves conceptual discipline.

---

# 62. Phase 1 — Function-Only MVP

Goals:

* DT-CG;
* RT-CG;
* trigger-localized unfolding;
* \(\Delta CG\);
* \(\Delta_U\);
* Markdown evidence report.

This should remain simple and executable.

---

# 63. Phase 2 — Validation Experiments

Goals:

* controlled gaps;
* bounded unfolding;
* trigger coverage;
* static vs unfolding comparison;
* gap benchmark.

This phase tests the central CGU hypothesis.

---

# 64. Phase 3 — Certification Runtime

Goals:

* C0–C5 evidence ladder;
* show-stop rules;
* evidence packages;
* residual risk;
* repeatable reports.

This turns CGU from analysis into assurance infrastructure.

---

# 65. Phase 4 — AI Coding Control Plane

Goals:

* graph segmentation;
* task creation;
* agent dispatch;
* local context construction;
* integration.

This tests the Design-Time CG control-plane concept.

---

# 66. Phase 5 — Structural Learning

Goals:

* recurring-gap detection;
* candidate structural differences;
* A/B validation;
* promotion;
* DT-CG evolution.

This connects CGU to continual learning.

---

# 67. Phase 6 — Condition / Context

Goals:

$$
F
\rightarrow
F+C
$$

Only introduce Condition/Context after measurable limitations of Function-only CGU are documented.

---

# 68. Phase 7 — Runtime State

Goals:

$$
F+C
\rightarrow
F+C+S
$$

Use State only where it adds clear predictive or certification value.

---

# 69. Phase 8 — Calling Structural Space

Long-term exploration:

$$
\mathcal{G}
$$

with:

$$
Projection
$$

and:

$$
Unfolding
$$

as separate operations.

This should be treated as a new research layer, not casually inserted into v1.0.

---

# 70. What Should Not Be Done Too Early

Several directions are attractive but should not be rushed.

Do not immediately create:

```text id="ig57jw"
One Giant Multi-Dimensional CallingGraph
```

Do not immediately claim:

```text id="r5rsrt"
Complete Behavioral Equivalence
```

Do not immediately turn:

$$
CertificationConfidence
$$

into an arbitrary probability.

Do not immediately use:

```text id="48wmf5"
Tensor
Quantum
State Space
```

terminology unless the mathematics requires it.

The CGU research program should remain:

$$
\boxed{
Operational\ First,
Formalization\ Second,
Expansion\ Third
}
$$

---

# 71. The Methodological Principle

Future development should follow:

$$
\boxed{
Add\ a\ Structural\ Dimension
Only\ When\ It\ Solves\ a\ Demonstrated\ Limitation
}
$$

This is more valuable than maximizing theoretical richness.

The purpose is not to make the model look sophisticated.

The purpose is to make it operationally stronger.

---

# 72. The Long-Term Research Question

The deepest future question is:

> **Can software structure become a persistent computational substrate that guides AI systems through design, execution, validation, certification, and learning?**

If the answer is yes, CallingGraph may evolve from:

$$
ProgramAnalysisArtifact
$$

into:

$$
\boxed{
Persistent\ Structural\ Runtime\ Infrastructure
}
$$

for AI coding.

---

# 73. From CallingGraph to Structural AI Coding

The larger research trajectory may therefore be:

$$
CallingGraph
$$

$$
\downarrow
$$

$$
CallingGraphUnfolding
$$

$$
\downarrow
$$

$$
DesignTimeCallingGraph
$$

$$
\downarrow
$$

$$
AI Coding Control Plane
$$

$$
\downarrow
$$

$$
StructuralCertification
$$

$$
\downarrow
$$

$$
StructuralLearning
$$

$$
\downarrow
$$

$$
StructuralAI\text{-}NativeSoftwareEngineering
$$

---

# 74. Final Future Map

```text id="e5905d"
CURRENT CGU v1.0
Function-Only CallingGraph
        |
        v
Executable Unfolding
        |
        v
Differential Validation
        |
        v
Certification Runtime
        |
        v
AI Coding Control Plane
        |
        v
Structural Learning
        |
        +-----------------------------+
        |                             |
        v                             v
Condition / Context             Better F-only Runtime
        |
        v
Runtime State
        |
        v
Projection / Policy
        |
        v
Calling Structural Space
        |
        v
Structural Runtime Paths
        |
        v
AI-Native Structural Software Engineering
```

---

# 75. Final Principle

The future of CGU should not be defined by adding complexity for its own sake.

It should be defined by turning structure into increasingly useful computational capability.

Therefore:

$$
\boxed{
\text{Do Not Enrich the Graph Indefinitely. Enrich Its Operational Power.}
}
$$

And for richer future models:

$$
\boxed{
\text{Do Not Enrich the Graph Indefinitely. Enrich Its Coordinate System.}
}
$$

---

## Current Boundary

CGU v1.0 remains:

$$
\boxed{
Function\text{-}Only
}
$$

All richer models described in this document are future research directions, not current formal claims.

---

## Recommended Next Engineering Step

$$
\boxed{
DT\text{-}CG
\rightarrow
TriggerLocalizedUnfolding
\rightarrow
RT\text{-}CG
\rightarrow
\Delta CG
\rightarrow
\Delta_U
\rightarrow
CertificationReport
}
$$

A small executable demonstration of this loop would be the most direct next validation of the CGU framework.

---

**CGU — CallingGraph Unfolding**

> **Build the Function-Only Runtime First.**

> **Expand Structure Only When the New Dimension Earns Its Place.**

> **Do Not Enrich the Graph Indefinitely; Enrich Its Coordinate System.**

> **Design. Unfold. Dispatch. Generate. Fold. Compare. Certify. Learn.**
