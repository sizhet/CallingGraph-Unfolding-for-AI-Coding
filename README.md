# CallingGraph Unfolding for AI Coding

## From Folded Program Structure to a Structural Control Plane for AI/ASI Coding

> **Design → Unfold → Simulate → Dispatch → Code → Fold → Compare → Certify → Learn**

**CGU — CallingGraph Unfolding**

---

## Overview

This repository presents a research framework for **CallingGraph Unfolding (CGU)**.

The project begins from a simple observation:

> A CallingGraph is not only a structural representation extracted from existing software.
> It can also serve as a folded functional structure that can be selectively unfolded, used for design-time planning, and later compared with the realized software structure.

The conventional CallingGraph direction is:

```text
Program
   |
   v
CallingGraph
   |
   v
Analysis
```

CGU introduces a broader lifecycle:

```text
Intent
   |
   v
Design-Time CallingGraph
   |
   v
Unfolding
   |
   v
Structural Wargaming
   |
   v
Task Segmentation
   |
   v
AI / Brain-Unit Dispatch
   |
   v
Localized Coding
   |
   v
Program
   |
   v
CallingGraph Folding
   |
   v
Realized CallingGraph
   |
   v
Differential Unfolding
   |
   v
Runtime Validation
   |
   v
Certification Confidence
   |
   v
Structural Learning
```

The central research transition is:

$$
\boxed{
CallingGraph:
\quad
Post\text{-}Hoc\ Program\ Representation
\quad\Longrightarrow\quad
Design\text{-}Time\ and\ Runtime\ Structural\ Control
}
$$

---

# 1. Core Idea

A program can be structurally folded into a CallingGraph:

$$
Program
\xrightarrow{Folding}
CG
$$

The CallingGraph retains selected functional relations while suppressing implementation detail.

CGU asks what happens in the other computational direction:

$$
CG
\xrightarrow{Unfolding}
Localized\ Functional\ Possibility
$$

Importantly:

$$
\boxed{
Unfolding
\neq
Inverse(Folding)
}
$$

CallingGraph Unfolding does not reconstruct the original program exactly.

Instead, it selectively expands a relevant functional region under a trigger, task, or structural focus.

The canonical pattern is:

$$
\boxed{
Folded\ Structure
+
Trigger
\rightarrow
Localization
\rightarrow
Unfolding
}
$$

---

# 2. Function-Only Foundation

CGU v1.0 deliberately begins with the simplest CallingGraph model:

$$
\boxed{
F=Function
}
$$

Let:

$$
CG_F=(V_F,E_F)
$$

where:

* \(V_F\) = callable functional units;
* \(E_F\) = calling relations.

This repository intentionally does **not** begin by adding Condition, State, Policy, Time, Probability, or other dimensions.

The first research objective is to determine how far a **Function-only CallingGraph** can already support:

* structural localization;
* unfolding;
* pre-coding planning;
* structural simulation;
* AI coding decomposition;
* agent dispatch;
* differential validation;
* certification;
* structural learning.

Richer dimensions are reserved for future work.

---

# 3. CallingGraph as Folding

A CallingGraph can be interpreted as a folded functional representation:

$$
Program
\rightarrow
CG_F
$$

For example:

```text
Controller
    |
    v
Validator
    |
    v
Service
    |
    v
Repository
    |
    v
Database
```

This structure suppresses many source-code details while retaining functional topology.

Therefore:

> **CallingGraph Folding is structural compression, not byte compression.**

The important result is not only a smaller representation.

It is a reusable structural object.

---

# 4. CallingGraph Unfolding

Given a trigger \(t\):

$$
U(CG,t)
$$

returns a localized functional expansion.

For example:

```text
Large CallingGraph
        |
        | Trigger:
        | "Investigate rollback"
        v
 Transaction Region
        |
        v
Authorization
        |
        v
Transaction
        |
        v
Rollback
```

The goal is not:

```text
Expand Everything
```

but:

```text
Trigger
   |
   v
Structural Hotspot
   |
   v
Localized Unfolding
```

Thus:

$$
Cost(U)
$$

should ideally depend more on the relevant local structural region than on the entire program universe.

---

# 5. From Two-Phase Search to Trigger-Localized Unfolding

CGU places CallingGraph Unfolding in a broader structural lineage:

$$
\boxed{
Full\text{-}Universe\ Search
\rightarrow
Two\text{-}Phase\ Search
\rightarrow
Structural\ Localization
\rightarrow
Trigger\text{-}Localized\ Unfolding
}
$$

Two-Phase Search introduces:

$$
Universe
\rightarrow
Candidate\ Space
\rightarrow
Target
$$

CGU advances the idea toward:

$$
Folded\ Structure
\rightarrow
Structural\ Hotspot
\rightarrow
Localized\ Expansion
$$

The central transition is:

$$
\boxed{
Explicit\ Universe\ Localization
\rightarrow
Pre\text{-}Folded\ Structural\ Localization
}
$$

Structure becomes reusable infrastructure rather than something rediscovered from the full universe for every task.

---

# 6. Design-Time CallingGraph

One of the central proposals of this repository is the:

$$
\boxed{
Design\text{-}Time\ CallingGraph
}
$$

or:

$$
\boxed{
DT\text{-}CG
}
$$

A Design-Time CallingGraph represents:

> **What the future software should structurally become before implementation is complete.**

The conventional direction is:

$$
Program
\rightarrow
CallingGraph
$$

The new direction is:

$$
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Program
$$

This changes the CallingGraph from an analysis artifact into a **generative structural skeleton**.

---

# 7. Structural Wargaming Before Coding

Once a DT-CG exists, it can be unfolded before implementation.

This enables:

$$
\boxed{
Structural\ Wargaming
}
$$

The system can ask:

* Which functional paths exist?
* Which paths are missing?
* Where are critical dependencies?
* Can the design be decomposed?
* Are alternative plans preferable?
* Which structural regions are risky?
* Which regions need specialist implementation?

The process becomes:

```text
Requirement
    |
    v
Design-Time CallingGraph
    |
    v
Unfold
    |
    v
Simulate
    |
    v
Detect Gaps
    |
    v
Revise Design
    |
    v
Code
```

This moves structural reasoning upstream.

---

# 8. Primary and Alternative Plans

A complex coding task may support multiple structural designs:

$$
DT\text{-}CG_A
$$

$$
DT\text{-}CG_B
$$

$$
DT\text{-}CG_C
$$

representing:

```text
Primary Plan
Alternative Plan
Fallback Plan
```

Each can be unfolded and compared before implementation.

This enables:

$$
\boxed{
Structural\ A/B\ Planning
}
$$

and potentially:

$$
\boxed{
Structural\ Plan\ Switching
}
$$

during execution.

---

# 9. Structure Before Agents

A central organizational principle of CGU is:

$$
\boxed{
Structure
\rightarrow
Organization
\rightarrow
Agents
}
$$

rather than:

$$
Agents
\rightarrow
Organization
$$

A large DT-CG can first be segmented into bounded functional regions:

$$
G_1,G_2,\dots,G_n
$$

Then those regions can be dispatched to appropriate coding units:

$$
G_i
\rightarrow
Agent_j
$$

This creates structurally grounded multi-agent AI coding.

---

# 10. Localized AI Coding

Each coding unit operates on a bounded structural region:

$$
Task_i
\rightarrow
CG_i
\rightarrow
LocalizedContext_i
\rightarrow
Agent_i
\rightarrow
Code_i
$$

The goal is not merely smaller prompts.

The context is selected according to **functional topology**.

This can potentially improve:

* focus;
* modularity;
* coordination;
* traceability;
* verification.

---

# 11. CallingGraph as an AI Coding Control Plane

The CallingGraph therefore begins to serve multiple roles:

```text
Planning
Simulation
Localization
Segmentation
Dispatch
Coordination
Validation
Certification
Repair
Learning
```

This motivates the central architecture:

$$
\boxed{
CallingGraph = AI\ Coding\ Structural\ Control\ Plane
}
$$

The control plane organizes the coding execution plane.

It does not replace the LLM or coding agent.

It gives generative intelligence a structural operating environment.

---

# 12. Control Plane vs Execution Plane

### Structural Control Plane

Responsible for:

* Design-Time CG;
* unfolding;
* task segmentation;
* dispatch;
* structural boundaries;
* comparison;
* certification decisions.

### Coding Execution Plane

Responsible for:

* reasoning;
* implementation;
* code generation;
* local testing;
* repair.

Conceptually:

```text
        STRUCTURAL CONTROL PLANE
                DT-CG
                  |
       +----------+----------+
       |          |          |
       v          v          v
    AI Unit    AI Unit    AI Unit
       |          |          |
       v          v          v
      Code       Code       Code
       \          |          /
        +---------+---------+
                  |
                  v
               Program
```

---

# 13. Folding the Result Back

After AI coding:

$$
Program
\xrightarrow{Folding}
RT\text{-}CG
$$

where:

$$
RT\text{-}CG
$$

is the Runtime / Realized CallingGraph.

This creates a design-to-realization loop:

$$
\boxed{
DT\text{-}CG
\rightarrow
Code
\rightarrow
RT\text{-}CG
}
$$

The intended and realized structures can now be compared.

---

# 14. Design-Time CG vs Realized CG

Static structural difference is:

$$
\boxed{
\Delta CG = DT\text{-}CG
\ominus
RT\text{-}CG
}
$$

Possible differences include:

* missing nodes;
* unexpected nodes;
* missing edges;
* unexpected edges;
* broken paths;
* unexpected dependencies.

But static comparison is only one level.

---

# 15. The Unfolding Gap

A central result of CGU is:

$$
\boxed{
CG_A
\approx
CG_B
\not\Rightarrow
U(CG_A,t) = U(CG_B,t)
}
$$

Two CallingGraphs can appear similar while producing different localized functional expansions.

We define:

$$
\boxed{
\Delta_U(t) = U(CG_A,t)
\ominus
U(CG_B,t)
}
$$

as the:

$$
\boxed{
Unfolding\ Gap
}
$$

Therefore:

$$
\boxed{
CallingGraph\ Similarity
\neq
Unfolding\ Equivalence
\neq
Runtime\ Equivalence
}
$$

---

# 16. Differential Unfolding

For Design-Time and Realized CallingGraphs:

$$
U(DT\text{-}CG,t)
$$

and:

$$
U(RT\text{-}CG,t)
$$

can be expanded under the same trigger.

Then:

$$
\Delta_U(t)
$$

can reveal hidden differences.

This process is called:

$$
\boxed{
Differential\ Unfolding
}
$$

For trigger set:

$$
T=\{t_1,t_2,\dots,t_n\}
$$

we compare:

$$
U(DT\text{-}CG,T)
\leftrightarrow
U(RT\text{-}CG,T)
$$

---

# 17. Why Static Match Is Not Universal Proof

A CallingGraph is a folded representation.

Folding is generally lossy.

Therefore:

$$
F(X)=F(Y)
$$

does not necessarily imply:

$$
X=Y
$$

Likewise:

$$
DT\text{-}CG = RT\text{-}CG
$$

does not prove total behavioral equivalence.

Static CallingGraph match should therefore be interpreted as:

$$
\boxed{
Structural\ Evidence
}
$$

rather than:

$$
\boxed{
Universal\ Proof
}
$$

---

# 18. The Open-Unfolding Problem

Suppose:

$$
\forall t\in T_{tested},
\quad
\Delta_U(t)=0
$$

There may still exist:

$$
t^*
\notin
T_{tested}
$$

such that:

$$
\Delta_U(t^*)\neq0
$$

This is the:

$$
\boxed{
Open\text{-}Unfolding\ Problem
}
$$

Therefore:

$$
\boxed{
No\ Gap\ Found
\neq
No\ Gap\ Exists
}
$$

under bounded structural testing.

---

# 19. Confidence-Based Certification

This leads to a stronger interpretation of AI coding certification.

Instead of:

```text
Certified = True / False
```

the system should ask:

> What evidence supports the certification claim?

The canonical evidence model is:

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

---

# 20. Evidence-Bounded Certification

CGU defines:

> **Evidence-Bounded Certification** as a certification claim whose scope and confidence are explicitly bounded by the structural and runtime evidence actually collected.

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

A certificate should explain:

* what was compared;
* what was unfolded;
* what was tested;
* what was not tested;
* what gaps were found;
* what deviations were approved;
* what residual risk remains.

---

# 21. Certification Ladder

CGU proposes the following evidence ladder.

| Level  | Evidence                               |
| ------ | -------------------------------------- |
| **C0** | Syntax / Compilation                   |
| **C1** | Static CallingGraph Match              |
| **C2** | Differential Structural Validation     |
| **C3** | Differential Unfolding + Coverage      |
| **C4** | Runtime Trajectory Validation          |
| **C5** | Integrated Evidence-Bounded Confidence |

The ladder represents increasing:

$$
\boxed{
Assurance\ Evidence\ Depth
}
$$

not increasing intrinsic correctness.

---

# 22. Structural Show-Stoppers

Aggregate similarity cannot override critical structural failures.

Examples include:

* required authorization path missing;
* required persistence path missing;
* forbidden dependency present;
* critical functional path broken;
* required service unreachable.

Therefore a certification system may define:

$$
ShowStop=True
\Rightarrow
Reject/Escalate
$$

regardless of an overall similarity score.

---

# 23. Certification as an Evidence Package

A useful certificate should not simply report:

```text
PASS
```

or:

```text
Score: 95
```

Instead:

```text
Design-Time CG:
Realized CG:

Static Delta:
Unfolding Delta:

Trigger Coverage:
Node Coverage:
Edge Coverage:
Depth Coverage:

Runtime Evidence:

Critical Gaps:
Approved Deviations:
Residual Risks:

Certification Level:
Certification Confidence:
Decision:
```

Thus:

$$
\boxed{
Certificate = Inspectable\ Evidence\ Package
}
$$

---

# 24. Certification as Control

Certification can become operational.

A result may trigger:

```text
Accept
Repair
Escalate
Replan
Reject
```

Therefore:

$$
\boxed{
Structural\ Evidence
\rightarrow
Certification
\rightarrow
Control
}
$$

Certification is no longer only an end-of-process score.

It becomes part of the AI coding control loop.

---

# 25. Gap-Driven Repair

Suppose the intended path is:

```text
B -> C -> D
```

but the realized path is:

```text
B -> D
```

The system can identify:

```text
Missing Functional Unit: C
```

and create a localized repair task.

Thus:

$$
\Delta_U
\rightarrow
Localization
\rightarrow
Repair
$$

This is more precise than regenerating a large module.

---

# 26. Repair vs Replanning

Not every difference means the realized program is wrong.

Sometimes:

$$
RT\text{-}CG
$$

reveals a better structure.

Then the correct action may be:

$$
Update(DT\text{-}CG)
$$

instead of:

$$
Force(RT\text{-}CG\rightarrow DT\text{-}CG)
$$

CGU therefore supports:

$$
Repair
$$

and:

$$
Replanning
$$

as distinct operations.

---

# 27. Structural Learning

After repeated coding campaigns, differences can become learning signals.

Suppose:

$$
DT:
A\rightarrow B\rightarrow C
$$

repeatedly becomes:

$$
RT:
A\rightarrow B\rightarrow X\rightarrow C
$$

Then:

$$
X
$$

may represent missing design knowledge.

The learning loop becomes:

$$
\boxed{
RecurringGap
\rightarrow
CandidateStructure
\rightarrow
A/B
\rightarrow
Validation
\rightarrow
Promotion
\rightarrow
BetterDT\text{-}CG
}
$$

---

# 28. The Complete AI Coding Campaign

The integrated lifecycle is:

```text
1. Intent
       |
       v
2. Design-Time CallingGraph
       |
       v
3. Structural Unfolding
       |
       v
4. Structural Wargaming
       |
       v
5. Primary / Alternative Plan
       |
       v
6. Structural Segmentation
       |
       v
7. AI / Brain-Unit Dispatch
       |
       v
8. Localized Coding
       |
       v
9. Program
       |
       v
10. CallingGraph Folding
       |
       v
11. Realized CallingGraph
       |
       v
12. Delta-CG
       |
       v
13. Differential Unfolding
       |
       v
14. Delta-U
       |
       v
15. Runtime Validation
       |
       v
16. Certification Confidence
       |
       +------> Accept
       +------> Repair
       +------> Escalate
       +------> Replan
       |
       v
17. Structural Learning
       |
       v
18. Better Design-Time CallingGraph
```

---

# 29. The CGU Grand Equation

The entire project can be summarized as:

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

# 30. The Six Core Papers

## CGU-001 — CallingGraph Unfolding

**From Folded Program Structure to Localized Functional Possibility**

Introduces:

* CallingGraph as Folding;
* Unfolding;
* Trigger-Localized Unfolding;
* CallingGraph Unfolding Space;
* Function-only foundation.

Core:

$$
Program
\rightarrow
CG
\rightarrow
LocalizedFunctionalPossibility
$$

---

## CGU-002 — From Two-Phase Search to Trigger-Localized Unfolding

Establishes:

$$
FullUniverse
\rightarrow
CandidateSpace
\rightarrow
StructuralHotspot
\rightarrow
LocalizedUnfolding
$$

and explains the transition from:

$$
ExplicitUniverseLocalization
$$

to:

$$
PreFoldedStructuralLocalization
$$

---

## CGU-003 — Design-Time CallingGraph

**Structural Wargaming for AI/ASI Coding**

Introduces:

* DT-CG;
* structural wargaming;
* primary and alternative plans;
* structural segmentation;
* agent dispatch;
* structural provenance.

Core:

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

## CGU-004 — The Unfolding Gap

Introduces:

$$
\Delta_U
$$

and establishes:

$$
\boxed{
CGMatch
\neq
UnfoldingEquivalence
\neq
RuntimeEquivalence
}
$$

It also introduces the Open-Unfolding Problem.

---

## CGU-005 — Differential Unfolding and Certification

Develops:

$$
\Delta CG
+
\Delta_U
+
Coverage
+
RuntimeEvidence
\rightarrow
CertificationConfidence
$$

and introduces Evidence-Bounded Certification.

---

## CGU-006 — CallingGraph as an AI Coding Control Plane

Integrates the complete lifecycle:

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

---

# 31. Figure Pack

The repository includes seven core diagrams.

## Fig-000 — CallingGraph Unfolding Grand Map

```text
Intent
  ->
Design-Time CG
  ->
Unfolding
  ->
Structural Wargaming
  ->
AI Units
  ->
Code
  ->
Realized CG
  ->
Differential Unfolding
  ->
Certification
  ->
Learning
```

![Fig-000 — CallingGraph Unfolding Grand Map](docs/figures/Fig-000-CallingGraph-Unfolding-Grand-Map.png)

---

## Fig-001 — Folding and Unfolding

Illustrates:

$$
Program
\rightarrow
CG
\rightarrow
LocalizedFunctionalPossibility
$$

and emphasizes:

$$
Unfolding
\neq
Inverse(Folding)
$$

![Fig-001 — Folding and Unfolding](docs/figures/Fig-001-Folding-and-Unfolding.png)

---

## Fig-002 — Two-Phase Search to Trigger Unfolding

Shows the evolution:

$$
FullSearch
\rightarrow
TwoPhaseSearch
\rightarrow
TriggerLocalizedUnfolding
$$

![Fig-002 — Two-Phase Search to Trigger Unfolding](docs/figures/Fig-002-Two-Phase-to-Trigger-Unfolding.png)

---

## Fig-003 — Design-Time CG Wargaming

Shows:

```text
Requirement
   ->
DT-CG
   ->
Primary / Alternative Plans
   ->
Structural Simulation
   ->
Agent Dispatch
```

![Fig-003 — Design-Time CG Wargaming](docs/figures/Fig-003-Design-Time-CG-Wargaming.png)

---

## Fig-004 — Design-Time CG vs Runtime CG

Illustrates:

$$
DT\text{-}CG
\leftrightarrow
RT\text{-}CG
$$

with:

$$
\Delta CG
$$

and:

$$
\Delta_U
$$

![Fig-004 — Design-Time CG vs Runtime CG](docs/figures/Fig-004-Design-Time-vs-Runtime-CG.png)

---

## Fig-005 — The Unfolding Gap

Shows why:

$$
CG_A
\approx
CG_B
$$

may still produce:

$$
U(CG_A,t)
\neq
U(CG_B,t)
$$

![Fig-005 — The Unfolding Gap](docs/figures/Fig-005-Unfolding-Gap.png)

---

## Fig-006 — AI Coding Campaign Loop

Integrates:

```text
Plan
 -> Unfold
 -> Dispatch
 -> Code
 -> Fold
 -> Compare
 -> Certify
 -> Learn
 -> Better Plan
```

![Fig-006 — AI Coding Campaign Loop](docs/figures/Fig-006-AI-Coding-Campaign-Loop.png)

---

# 32. Repository Structure

```text
CallingGraph-Unfolding-for-AI-Coding/
│
├── README.md
├── START-HERE.md
├── CONTENTS.md
├── CITATION.cff
├── .zenodo.json
├── LICENSE
└── docs/
    ├── FIGURE-INDEX.md
    ├── GLOSSARY.md
    ├── FUTURE-DIRECTIONS.md
    ├── CGU-001-CallingGraph-Unfolding.md
    ├── CGU-002-Two-Phase-Search-to-Trigger-Localized-Unfolding.md
    ├── CGU-003-Design-Time-CallingGraph.md
    ├── CGU-004-The-Unfolding-Gap.md
    ├── CGU-005-Differential-Unfolding-and-Certification.md
    ├── CGU-006-CallingGraph-as-AI-Coding-Control-Plane.md
    └── figures/
        ├── Fig-000-CallingGraph-Unfolding-Grand-Map.png
        ├── Fig-001-Folding-and-Unfolding.png
        ├── Fig-002-Two-Phase-to-Trigger-Unfolding.png
        ├── Fig-003-Design-Time-CG-Wargaming.png
        ├── Fig-004-Design-Time-vs-Runtime-CG.png
        ├── Fig-005-Unfolding-Gap.png
        └── Fig-006-AI-Coding-Campaign-Loop.png
```

---

# 33. Key Concepts

### CallingGraph Folding

$$
Program
\rightarrow
CallingGraph
$$

Structural compression of program functionality.

---

### CallingGraph Unfolding

$$
CallingGraph
+
Trigger
\rightarrow
LocalizedFunctionalPossibility
$$

Selective functional expansion.

---

### Trigger-Localized Unfolding

$$
Trigger
\rightarrow
Hotspot
\rightarrow
BoundedExpansion
$$

---

### Design-Time CallingGraph

$$
Intent
\rightarrow
DT\text{-}CG
$$

Intended functional structure before coding.

---

### Realized CallingGraph

$$
Program
\rightarrow
RT\text{-}CG
$$

Functional structure extracted after implementation.

---

### Structural Delta

$$
\Delta CG = DT\text{-}CG
\ominus
RT\text{-}CG
$$

---

### Unfolding Gap

$$
\Delta_U = U(DT\text{-}CG,T)
\ominus
U(RT\text{-}CG,T)
$$

---

### Differential Unfolding

Paired localized expansion and comparison of design-time and realized CallingGraphs.

---

### Evidence-Bounded Certification

Certification whose claims are explicitly bounded by:

* evidence;
* coverage;
* runtime validation;
* residual uncertainty.

---

### AI Coding Control Plane

A CallingGraph-based structural layer organizing:

* planning;
* localization;
* dispatch;
* generation;
* validation;
* certification;
* learning.

---

# 34. Canonical Statements

> **A CallingGraph is not only a folded representation of existing software; it can also serve as a generative structural skeleton for future software.**

> **CallingGraph Unfolding is the trigger-localized expansion of folded functional structure into a bounded functional possibility space.**

> **Design-Time CallingGraph moves AI coding control from token generation toward structural campaign planning.**

> **Structure should determine organization, and organization should determine agent dispatch.**

> **CallingGraph similarity is structural evidence, not universal proof.**

> **What looks the same when folded may differ when unfolded.**

> **Certify the evidence, not just the similarity.**

> **Move AI Coding control upstream—from Token Generation to Structural Planning.**

---

# 35. What CGU Is Not

CGU is not intended to claim that:

```text
CallingGraph = Complete Program Semantics
```

or:

```text
CallingGraph Match = Universal Behavioral Proof
```

or:

```text
Function-Only CG = Complete AI Coding Governance
```

Instead, CGU establishes a practical structural foundation that can later be extended.

The v1.0 scope remains intentionally narrow:

$$
\boxed{
Function\ Only
}
$$

---

# 36. Future Directions

Potential future structural extensions include:

$$
F
\rightarrow
F+C
\rightarrow
F+C+S
$$

where:

* **F** = Function;
* **C** = Condition / Context;
* **S** = Runtime State.

A possible future operator is:

$$
P = Projection / Policy
$$

A richer future model may explore:

$$
CallingStructuralSpace
\xrightarrow{Projection}
LocalizedCallingGraph
\xrightarrow{Unfolding}
StructuralTrajectory
$$

This raises a deeper question:

> **Is a conventional CallingGraph really the complete structural object, or is it a functional projection of a richer Calling Structural Space?**

This question is intentionally outside the scope of CGU v1.0.

---

# 37. Research Questions

CGU opens several research directions:

1. How should requirements be converted automatically into Design-Time CallingGraphs?
2. How should CallingGraph Unfolding triggers be generated?
3. How should unfolding depth and bounds be selected?
4. How should DT-CGs be structurally compared before coding?
5. How should large CallingGraphs be segmented into AI coding units?
6. How should subgraphs be matched to specialist AI / Brain Units?
7. How accurately can generated code be folded back into RT-CG?
8. How should \(\Delta CG\) and \(\Delta_U\) be measured?
9. How should certification coverage be quantified?
10. How should certification evidence influence repair and replanning?
11. How should recurring Unfolding Gaps become structural learning signals?
12. Can Function-only CGU measurably improve large-scale AI coding quality and coordination?

---

# 38. Recommended Reading Order

For first-time readers:

```text
CGU-001
   |
   v
CGU-002
   |
   v
CGU-003
   |
   v
CGU-004
   |
   v
CGU-005
   |
   v
CGU-006
```

The conceptual progression is:

```text
Folding
   ->
Unfolding
   ->
Localization
   ->
Design-Time CG
   ->
Structural Wargaming
   ->
Unfolding Gap
   ->
Differential Validation
   ->
Certification
   ->
Control Plane
```

---

# 39. Who This Repository Is For

This project may be useful to researchers and engineers working on:

* AI Coding;
* Autonomous Software Engineering;
* Multi-Agent Coding Systems;
* CallingGraph Analysis;
* Program Structure;
* Software Architecture;
* Structural Verification;
* AI Coding Certification;
* AI Coding Governance;
* Structural Continual Learning;
* AI/ASI Control Planes.

---

# 40. The CGU Research Position

CGU is not primarily proposing:

```text
a new graph visualization
```

or:

```text
a new post-coding score
```

The broader proposal is:

$$
\boxed{
CallingGraph:
Analysis\ Artifact
\rightarrow
Lifecycle\ Structural\ Infrastructure
}
$$

The key research object becomes:

$$
\boxed{
How\ CallingGraph\ Unfolding\ can\ organize\ AI\ Coding\ itself
}
$$

Certification is one important stage inside that broader lifecycle.

---

# 41. CGU Grand Map

The complete paradigm can be summarized as:

$$
\boxed{
Intent
\rightarrow
Design\text{-}Time\ CG
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
Realized\ CG
\rightarrow
Differential\ Unfolding
\rightarrow
Runtime\ Validation
\rightarrow
Certification
\rightarrow
Learn
}
$$

---

# 42. CGU Grand Principle

$$
\boxed{
\text{Design. Unfold. Dispatch. Generate. Fold. Compare. Certify. Learn.}
}
$$

And the deeper architectural transition is:

$$
\boxed{
\text{Move AI Coding Control Upstream—from Token Generation to Structural Planning.}
}
$$

---

## Status

**CGU v1.0**

Current scope:

$$
\boxed{
Function\text{-}Only\ CallingGraph
}
$$

The repository establishes the theoretical foundation for CallingGraph Unfolding, Design-Time CallingGraphs, Differential Unfolding, and confidence-based structural certification.

The next stage is expected to move increasingly toward:

* minimal executable CGU demos;
* DT-CG construction;
* trigger-localized unfolding algorithms;
* Design-Time vs Realized CG comparison;
* Differential Unfolding experiments;
* certification reports;
* and eventually richer CallingGraph dimensions.

---

## Citation

Citation metadata will be provided through:

```text
CITATION.cff
.zenodo.json
```

after repository release metadata is finalized.

---

## License

See the repository `LICENSE` file.

---

**CGU — CallingGraph Unfolding**

> **Fold Structure. Localize Relevance. Unfold Possibility.**

> **Design the Structure Before Generating the Code.**

> **Certify the Evidence, Not Just the Similarity.**

> **Design. Unfold. Dispatch. Generate. Fold. Compare. Certify. Learn.**


---

## Author

Sizhe Tan\
Independent Researcher

GPT-Obot\
AI Research Assistant

2026

DOI: TBD
    
---

## 📚 DBM-SI Series Navigation

See:\
[./docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Series-of-gitHub-Repositories.md](./docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Series-of-gitHub-Repositories.md)

[./docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Structural-Intelligence-Dictionary-(v2).md](./docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Structural-Intelligence-Dictionary-(v2).md)

