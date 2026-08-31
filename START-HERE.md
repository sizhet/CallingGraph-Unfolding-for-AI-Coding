# START HERE — CallingGraph Unfolding for AI Coding

## A 10–15 Minute Guide to CGU

**Project:** CallingGraph Unfolding for AI Coding
**Short Name:** CGU — CallingGraph Unfolding
**Version:** v1.0
**Scope:** Function-Only CallingGraph

---

# 1. Start with One Question

A CallingGraph is normally created **after** a program exists:

```text
Program
   |
   v
CallingGraph
   |
   v
Analysis
```

It tells us something about the functional structure of existing software:

* which function calls which;
* which functional paths exist;
* which modules depend on which;
* where important structural regions are located.

But this repository begins with a different question:

> **If a program can be structurally folded into a CallingGraph, can the CallingGraph also be selectively unfolded and used before and during AI coding?**

That question leads to:

$$
\boxed{
CallingGraph\ Unfolding
}
$$

or:

$$
\boxed{
CGU
}
$$

---

# 2. The First Idea: CallingGraph as Folding

Consider a large program.

It contains:

* source code;
* functions;
* classes;
* parameters;
* variables;
* data;
* branches;
* exceptions;
* libraries;
* runtime behavior;
* implementation details.

A CallingGraph suppresses much of this information and preserves selected functional relationships.

Conceptually:

$$
Program
\xrightarrow{Folding}
CallingGraph
$$

For example:

```text
Thousands of lines of code
          |
          v
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

The CallingGraph is therefore a form of:

$$
\boxed{
Structural\ Folding
}
$$

It is not byte compression.

It is not source-code compression.

It is a reduction of a large implementation universe into a smaller functional structural representation.

---

# 3. The Second Idea: Folding Suggests Unfolding

Once CallingGraph is understood as Folding, another question appears naturally:

> What can be done in the other direction?

Not:

$$
CallingGraph
\rightarrow
ExactOriginalProgram
$$

because CallingGraph Folding is generally lossy.

Instead:

$$
CallingGraph
\rightarrow
LocalizedFunctionalPossibility
$$

CGU calls this:

$$
\boxed{
CallingGraph\ Unfolding
}
$$

The crucial rule is:

$$
\boxed{
Unfolding
\neq
Inverse(Folding)
}
$$

Unfolding does not reconstruct everything that was removed during Folding.

It activates and expands relevant functional structure.

---

# 4. Trigger-Localized Unfolding

CGU does not propose unfolding an entire large CallingGraph every time.

Instead:

$$
Trigger
\rightarrow
Localization
\rightarrow
Unfolding
$$

Suppose a large system contains:

```text
Authentication
Payment
Inventory
Logging
Notification
Database
Reporting
Recovery
```

and the current task is:

```text
Investigate payment rollback
```

The system should not reason equally over the entire graph.

It should locate a relevant structural region:

```text
Payment
   |
   v
Transaction
   |
   v
Persistence
   |
   v
Rollback
```

and unfold around that hotspot.

Therefore:

$$
\boxed{
CGU
=
Trigger\text{-}Localized\ Structural\ Expansion
}
$$

---

# 5. Why Two-Phase Search Matters

CallingGraph Unfolding did not appear from nowhere.

There is a broader structural progression:

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

A conventional search problem may begin with:

$$
Universe
\rightarrow
Target
$$

Two-Phase Search introduces an intermediate candidate space:

$$
Universe
\rightarrow
CandidateSpace
\rightarrow
Target
$$

CGU goes further.

Much of the localization knowledge can already be encoded in structural form:

$$
FoldedStructure
\rightarrow
Hotspot
\rightarrow
LocalizedExpansion
$$

The transition is:

$$
\boxed{
Explicit\ Universe\ Localization
\rightarrow
Pre\text{-}Folded\ Structural\ Localization
}
$$

This is one reason CallingGraphs may become computationally important beyond conventional program analysis.

---

# 6. The Major Turn: Design-Time CallingGraph

This repository makes a second major move.

CallingGraphs do not need to exist only after coding.

We can define:

$$
\boxed{
DT\text{-}CG
=
Design\text{-}Time\ CallingGraph
}
$$

The DT-CG describes:

> **What the future software should structurally become.**

Now the direction changes from:

$$
Program
\rightarrow
CallingGraph
$$

to:

$$
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Program
$$

This is one of the most important ideas in CGU.

---

# 7. From Analysis Artifact to Generative Skeleton

Traditionally:

$$
CallingGraph
=
Representation\ of\ Existing\ Software
$$

CGU adds:

$$
CallingGraph
=
Structural\ Skeleton\ for\ Future\ Software
$$

The DT-CG does not specify every source-code token.

Instead, it specifies functional structure.

For example:

```text
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
   |
   v
Audit
```

An AI coding system can then implement this structure.

Thus:

$$
\boxed{
DT\text{-}CG
\rightarrow
Constrained\ Program\ Possibility\ Space
}
$$

rather than:

$$
DT\text{-}CG
\rightarrow
One\ Exact\ Program
$$

---

# 8. Structural Wargaming

Once a CallingGraph exists before coding, we can simulate structure before implementation.

CGU calls this:

$$
\boxed{
Structural\ Wargaming
}
$$

The workflow becomes:

```text
Requirement
    |
    v
DT-CG
    |
    v
Unfold
    |
    v
Inspect Functional Paths
    |
    v
Find Missing / Weak Structure
    |
    v
Revise DT-CG
    |
    v
Code
```

Before expensive implementation begins, we can ask:

* Is a required function missing?
* Is a critical path incomplete?
* Is one module overloaded?
* Is a dependency unnecessary?
* Can the system be decomposed more cleanly?
* Should an alternative structural plan be prepared?

This is **pre-coding structural simulation**.

---

# 9. Primary and Alternative Plans

A difficult software problem may have several plausible designs:

$$
DT\text{-}CG_A
$$

$$
DT\text{-}CG_B
$$

$$
DT\text{-}CG_C
$$

These may represent:

```text
Primary Plan
Alternative Plan
Fallback Plan
```

Instead of discovering architectural problems only after implementation, CGU allows the structures themselves to be compared.

Conceptually:

$$
DT\text{-}CG_A
\leftrightarrow
DT\text{-}CG_B
$$

followed by:

$$
U(DT\text{-}CG_A,T)
\leftrightarrow
U(DT\text{-}CG_B,T)
$$

This creates:

$$
\boxed{
Structural\ A/B\ Planning
}
$$

before coding.

---

# 10. From Structure to AI Organization

The DT-CG also provides a natural way to organize multiple AI coding units.

A large graph can be segmented:

$$
DT\text{-}CG
\rightarrow
\{G_1,G_2,\dots,G_n\}
$$

Each subgraph becomes a bounded coding task.

Then:

$$
G_i
\rightarrow
Agent_j
$$

The organizational principle is:

$$
\boxed{
Structure
\rightarrow
Organization
\rightarrow
Agents
}
$$

not:

$$
Agents
\rightarrow
Organization
$$

The number and type of agents should follow the software structure.

---

# 11. Localized AI Coding

An agent does not necessarily need the entire project context.

Instead:

$$
DT\text{-}CG
\xrightarrow{Localization}
G_i
$$

then:

$$
G_i
+
RelevantContext_i
\rightarrow
Agent_i
\rightarrow
Code_i
$$

This produces:

$$
\boxed{
Localized\ AI\ Coding
}
$$

The local structural region acts as a functional boundary.

The AI remains free to make many implementation decisions inside that boundary.

This creates:

$$
\boxed{
Bounded\ Autonomy
}
$$

---

# 12. Folding the Implementation Back

After implementation, the generated program can again be folded:

$$
Program
\xrightarrow{Folding}
RT\text{-}CG
$$

where:

$$
\boxed{
RT\text{-}CG
=
Realized\ CallingGraph
}
$$

Now there are two structural objects:

### Intended Structure

$$
DT\text{-}CG
$$

### Realized Structure

$$
RT\text{-}CG
$$

This creates a natural validation interface.

---

# 13. The First Difference: ΔCG

We compare:

$$
DT\text{-}CG
$$

with:

$$
RT\text{-}CG
$$

and define:

$$
\boxed{
\Delta CG
=
DT\text{-}CG
\ominus
RT\text{-}CG
}
$$

Possible differences include:

```text
Missing Node
Unexpected Node
Missing Edge
Unexpected Edge
Broken Path
Unexpected Dependency
Forbidden Relation
```

This is already useful.

But it is not enough.

---

# 14. The Unfolding Gap

Suppose two CallingGraphs look nearly identical:

$$
CG_A
\approx
CG_B
$$

Does this imply that they behave identically when structurally activated?

No.

There may exist a trigger:

$$
t^*
$$

such that:

$$
U(CG_A,t^*)
\neq
U(CG_B,t^*)
$$

CGU defines:

$$
\boxed{
\Delta_U(t)
=
U(CG_A,t)
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

This leads to one of the central CGU statements:

$$
\boxed{
CallingGraph\ Match
\neq
Unfolding\ Equivalence
}
$$

and more broadly:

$$
\boxed{
CallingGraph\ Match
\neq
Runtime\ Equivalence
}
$$

---

# 15. Why This Matters for AI Coding Certification

Imagine that an AI generates a program.

Its CallingGraph matches the Design-Time CallingGraph extremely well:

```text
CG Similarity = 99.7%
```

Can we conclude:

```text
Program Correct = True
```

No.

The remaining difference may contain a critical missing path.

Even perfect static CallingGraph equality may not establish total behavioral equivalence because the CallingGraph is itself a folded representation.

Therefore:

$$
\boxed{
CG\ Match
=
Structural\ Evidence
}
$$

not automatically:

$$
\boxed{
Universal\ Proof
}
$$

---

# 16. Differential Unfolding

To strengthen validation, CGU proposes applying the same trigger set to both structures.

For:

$$
T=\{t_1,t_2,\dots,t_n\}
$$

compute:

$$
U(DT\text{-}CG,T)
$$

and:

$$
U(RT\text{-}CG,T)
$$

then compare:

$$
\boxed{
\Delta_U(T)
=
U(DT\text{-}CG,T)
\ominus
U(RT\text{-}CG,T)
}
$$

This is:

$$
\boxed{
Differential\ Unfolding
}
$$

It asks:

> When the same structural hotspots are activated, do the design and implementation unfold compatibly?

---

# 17. The Open-Unfolding Problem

Even Differential Unfolding has a boundary.

Suppose:

$$
\forall t\in T_{tested},
\quad
\Delta_U(t)=0
$$

There may still exist:

$$
t^*
\notin T_{tested}
$$

such that:

$$
\Delta_U(t^*)\neq0
$$

Therefore:

$$
\boxed{
No\ Observed\ Unfolding\ Gap
\neq
Universal\ Unfolding\ Equivalence
}
$$

This is the:

$$
\boxed{
Open\text{-}Unfolding\ Problem
}
$$

It is one reason certification must report coverage.

---

# 18. From Boolean Certification to Evidence-Bounded Confidence

Instead of claiming:

```text
Certified = True
```

CGU proposes:

$$
\boxed{
Evidence\text{-}Bounded\ Certification
}
$$

The core evidence chain is:

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

The question becomes:

> **How much evidence supports this certification claim, and what remains outside the tested boundary?**

---

# 19. Certification Ladder

CGU proposes six evidence levels.

| Level  | Certification Evidence                 |
| ------ | -------------------------------------- |
| **C0** | Syntax / Compilation                   |
| **C1** | Static CallingGraph Match              |
| **C2** | Differential Structural Validation     |
| **C3** | Differential Unfolding + Coverage      |
| **C4** | Runtime Trajectory Validation          |
| **C5** | Integrated Evidence-Bounded Confidence |

Important:

$$
\boxed{
C5
\neq
More\ Correct\ Than\ C4
}
$$

Instead:

$$
\boxed{
C5
=
Deeper\ Assurance\ Evidence
}
$$

---

# 20. The Certificate Should Preserve Evidence

A useful certificate should not contain only:

```text
PASS
```

or:

```text
Confidence = 94%
```

It should preserve evidence such as:

```text
DT-CG:
RT-CG:

Delta-CG:

Trigger Set:
Differential Unfolding:
Delta-U:

Trigger Coverage:
Node Coverage:
Edge Coverage:
Depth Coverage:

Runtime Evidence:

Critical Gaps:
Approved Deviations:
Residual Risks:

Certification Level:
Decision:
```

Thus:

$$
\boxed{
Certificate
=
Inspectable\ Evidence\ Package
}
$$

---

# 21. Certification Becomes a Control Signal

Once certification exists inside an AI coding system, it can produce actions:

```text
Accept
Repair
Escalate
Replan
Reject
```

Thus:

$$
StructuralEvidence
\rightarrow
Certification
\rightarrow
Control
$$

Certification is no longer only a final report.

It becomes part of the execution loop.

---

# 22. CallingGraph as an AI Coding Control Plane

We can now assemble the pieces.

CallingGraph supports:

### Before Coding

* structural design;
* alternative planning;
* structural wargaming;
* task decomposition.

### During Coding

* localization;
* segmentation;
* agent dispatch;
* structural boundaries;
* progress coordination.

### After Coding

* Folding;
* DT-CG vs RT-CG comparison;
* Differential Unfolding;
* runtime validation;
* certification;
* repair.

### Across Coding Campaigns

* gap accumulation;
* candidate structures;
* A/B validation;
* structural learning.

Therefore:

$$
\boxed{
CallingGraph
\rightarrow
AI\ Coding\ Structural\ Control\ Plane
}
$$

---

# 23. The Complete CGU Lifecycle

The entire framework can be read in one sequence:

```text
INTENT
   |
   v
DESIGN-TIME CALLINGGRAPH
   |
   v
UNFOLD
   |
   v
STRUCTURAL WARGAMING
   |
   v
SEGMENT
   |
   v
DISPATCH
   |
   v
LOCALIZED AI CODING
   |
   v
PROGRAM
   |
   v
FOLD
   |
   v
REALIZED CALLINGGRAPH
   |
   v
DELTA-CG
   |
   v
DIFFERENTIAL UNFOLDING
   |
   v
DELTA-U
   |
   v
RUNTIME VALIDATION
   |
   v
CERTIFICATION CONFIDENCE
   |
   +----> ACCEPT
   |
   +----> REPAIR
   |
   +----> ESCALATE
   |
   +----> REPLAN
   |
   v
STRUCTURAL LEARNING
   |
   v
BETTER DESIGN-TIME CALLINGGRAPH
```

---

# 24. The Canonical Equation

The complete CGU control cycle is:

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

This is the shortest mathematical summary of the repository.

---

# 25. Why This Is More Than CallingGraph QA

A narrow interpretation would be:

```text
AI writes code
      |
      v
CallingGraph checks code
```

CGU proposes something much larger:

```text
CallingGraph designs
      |
      v
CallingGraph localizes
      |
      v
CallingGraph dispatches
      |
      v
AI writes code
      |
      v
CallingGraph validates
      |
      v
CallingGraph helps certify
      |
      v
CallingGraph learns
```

Therefore:

$$
\boxed{
CGU
\neq
Post\text{-}Coding\ QA\ Only
}
$$

Instead:

$$
\boxed{
CGU
=
Pre\text{-}Coding\ Design
+
In\text{-}Coding\ Control
+
Post\text{-}Coding\ Assurance
}
$$

---

# 26. The Deepest Paradigm Shift

The most important transition in this repository may be:

$$
\boxed{
Prompt\text{-}Centered\ Coding
\rightarrow
Structure\text{-}Centered\ Coding
}
$$

or:

$$
\boxed{
Token\ Generation
\text{ as Control Center}
\rightarrow
Structural\ Planning
\text{ as Control Center}
}
$$

LLMs still generate code.

Agents still reason.

But their work occurs inside a structural organization.

---

# 27. What the CallingGraph Does Not Replace

CGU does **not** propose replacing:

* LLM reasoning;
* source code;
* testing;
* runtime validation;
* software architecture;
* human engineering judgment.

Instead, CallingGraph provides a structural layer connecting them.

Think of it as:

$$
\boxed{
Structural\ Coordination\ Infrastructure
}
$$

rather than a replacement for existing engineering mechanisms.

---

# 28. Why Function-Only Comes First

Many richer dimensions are possible.

A future CallingGraph-like structure might include:

* Condition;
* Context;
* State;
* Policy;
* Data;
* Time;
* Probability;
* Runtime history.

But putting all of these into the first model would make the research object difficult to isolate.

Therefore CGU v1.0 deliberately begins with:

$$
\boxed{
F=Function\ Only
}
$$

This allows us to ask a clean question:

> **How far can CallingGraph Unfolding go using only functional topology?**

The answer developed in this repository is already substantial.

Function-only structure can support:

* Folding;
* Unfolding;
* Localization;
* Design-Time CG;
* Structural Wargaming;
* Segmentation;
* Dispatch;
* Differential Validation;
* Certification;
* Repair;
* Learning.

That is enough for a strong first foundation.

---

# 29. Future Dimensions

After the Function-only foundation is understood, future work may explore:

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

A future:

$$
P
$$

may act as a:

$$
Projection / Policy\ Operator
$$

rather than simply another graph dimension.

A richer model might eventually become:

$$
CallingStructuralSpace
\xrightarrow{Projection}
LocalizedCallingGraph
\xrightarrow{Unfolding}
StructuralTrajectory
$$

This leads to an important future question:

> **Is a conventional CallingGraph really the complete object, or is it a visible functional projection of a richer Calling Structural Space?**

That question is intentionally deferred beyond CGU v1.0.

---

# 30. Read the Six Papers in This Order

## Step 1 — CGU-001

### `CGU-001-CallingGraph-Unfolding.md`

Read this first.

It establishes:

$$
Folding
$$

$$
Unfolding
$$

$$
TriggerLocalization
$$

and the Function-only CGU foundation.

If you read only one theoretical paper first, read this one.

---

## Step 2 — CGU-002

### `CGU-002-Two-Phase-Search-to-Trigger-Localized-Unfolding.md`

Read this to understand where the localization mechanism comes from.

It develops:

$$
FullUniverseSearch
\rightarrow
TwoPhaseSearch
\rightarrow
TriggerLocalizedUnfolding
$$

This paper provides the computational lineage.

---

## Step 3 — CGU-003

### `CGU-003-Design-Time-CallingGraph.md`

This is the major engineering transition.

It moves CallingGraph:

$$
PostCoding
\rightarrow
PreCoding
$$

and introduces:

* Design-Time CallingGraph;
* Structural Wargaming;
* primary / alternative plans;
* structural segmentation;
* agent dispatch.

If your main interest is **AI Coding**, this paper is essential.

---

## Step 4 — CGU-004

### `CGU-004-The-Unfolding-Gap.md`

This paper explains why static CallingGraph similarity is not enough.

Core:

$$
\boxed{
CGMatch
\neq
UnfoldingEquivalence
}
$$

and:

$$
\boxed{
\Delta_U
}
$$

This paper provides the theoretical bridge from Unfolding to Certification.

---

## Step 5 — CGU-005

### `CGU-005-Differential-Unfolding-and-Certification.md`

This paper develops:

$$
DT\text{-}CG
\leftrightarrow
RT\text{-}CG
$$

and:

$$
U(DT,T)
\leftrightarrow
U(RT,T)
$$

into an evidence-based certification architecture.

Core:

$$
\boxed{
\Delta CG
+
\Delta_U
+
Coverage
+
RuntimeEvidence
\rightarrow
CertificationConfidence
}
$$

---

## Step 6 — CGU-006

### `CGU-006-CallingGraph-as-AI-Coding-Control-Plane.md`

Read this last.

It integrates the complete framework:

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

This is the architectural synthesis of CGU v1.0.

---

# 31. If You Have Only Five Minutes

Read these three ideas.

### Idea 1

$$
\boxed{
Program
\xrightarrow{Folding}
CallingGraph
}
$$

but also:

$$
\boxed{
CallingGraph
\xrightarrow{Localized\ Unfolding}
FunctionalPossibility
}
$$

---

### Idea 2

Create the CallingGraph **before coding**:

$$
\boxed{
Intent
\rightarrow
DT\text{-}CG
\rightarrow
AI\ Coding
}
$$

and use it for structural planning and dispatch.

---

### Idea 3

After coding:

$$
Program
\rightarrow
RT\text{-}CG
$$

then compare:

$$
DT\text{-}CG
\leftrightarrow
RT\text{-}CG
$$

and:

$$
U(DT,T)
\leftrightarrow
U(RT,T)
$$

to build:

$$
\boxed{
Evidence\text{-}Bounded\ Certification
}
$$

These three ideas contain the backbone of CGU.

---

# 32. If You Are an AI Coding Researcher

Focus on:

```text
CGU-003
    |
    v
CGU-006
    |
    v
CGU-005
```

The key question is:

> **Can Design-Time CallingGraphs become an operational control structure for multi-agent AI coding?**

Pay particular attention to:

$$
Structure
\rightarrow
Organization
\rightarrow
Agents
$$

and:

$$
DT\text{-}CG
\rightarrow
LocalizedCodingTasks
$$

---

# 33. If You Are a Program Analysis Researcher

Focus on:

```text
CGU-001
    |
    v
CGU-002
    |
    v
CGU-004
```

The key questions are:

> What does Unfolding mean for a folded graph representation?

and:

> What structural differences remain hidden under static graph similarity?

---

# 34. If You Are Interested in Verification or Certification

Focus on:

```text
CGU-004
    |
    v
CGU-005
```

The key chain is:

$$
CGMatch
\not\Rightarrow
UnfoldingEquivalence
$$

therefore:

$$
StaticMatch
\rightarrow
DifferentialUnfolding
\rightarrow
Coverage
\rightarrow
RuntimeEvidence
\rightarrow
Confidence
$$

---

# 35. If You Are Interested in AI/ASI Architecture

Focus on:

```text
CGU-003
    |
    v
CGU-006
```

The main architectural question is:

> **Can structural planning become the control plane above specialized AI coding units?**

The paradigm is:

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

# 36. Seven Figures to Read

The repository includes seven core diagrams.

### Fig-000 — CallingGraph Unfolding Grand Map

Start here for the complete CGU landscape.

---

### Fig-001 — Folding and Unfolding

Use this to understand the fundamental two-direction structural relationship.

---

### Fig-002 — Two-Phase Search to Trigger-Localized Unfolding

Use this to understand the computational lineage.

---

### Fig-003 — Design-Time CG Wargaming

Use this to understand pre-coding structural planning.

---

### Fig-004 — Design-Time vs Runtime CG

Use this to understand the design-realization comparison.

---

### Fig-005 — Unfolding Gap

Use this to understand why static CG match is insufficient.

---

### Fig-006 — AI Coding Campaign Loop

Use this to understand the complete:

$$
Plan
\rightarrow
Execute
\rightarrow
Validate
\rightarrow
Learn
$$

cycle.

---

# 37. Seven Concepts to Remember

If you leave this repository remembering only seven terms, remember these:

```text
1. Folding
2. Unfolding
3. Trigger Localization
4. Design-Time CallingGraph
5. Unfolding Gap
6. Differential Unfolding
7. AI Coding Control Plane
```

Together they form the conceptual spine of CGU.

---

# 38. Six Equations to Remember

### 1. Folding

$$
\boxed{
Program
\xrightarrow{Folding}
CG
}
$$

### 2. Unfolding

$$
\boxed{
CG
\xrightarrow{Trigger}
U(CG,t)
}
$$

### 3. Design-Time Structure

$$
\boxed{
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Program
}
$$

### 4. Static Difference

$$
\boxed{
\Delta CG
=
DT\text{-}CG
\ominus
RT\text{-}CG
}
$$

### 5. Unfolding Gap

$$
\boxed{
\Delta_U(t)
=
U(DT\text{-}CG,t)
\ominus
U(RT\text{-}CG,t)
}
$$

### 6. Certification

$$
\boxed{
\Delta CG
+
\Delta_U
+
Coverage
+
RuntimeEvidence
\rightarrow
CertificationConfidence
}
$$

---

# 39. Four Statements to Remember

> **A CallingGraph is not only a folded representation of existing software; it can also serve as a generative structural skeleton for future software.**

> **Design-Time CallingGraph moves AI coding control from token generation toward structural campaign planning.**

> **What looks the same when folded may differ when unfolded.**

> **Certify the evidence, not just the similarity.**

---

# 40. One Paradigm to Remember

The complete CGU paradigm is:

$$
\boxed{
Design.
Unfold.
Dispatch.
Generate.
Fold.
Compare.
Certify.
Learn.
}
$$

Or operationally:

```text
DESIGN
   |
   v
UNFOLD
   |
   v
DISPATCH
   |
   v
GENERATE
   |
   v
FOLD
   |
   v
COMPARE
   |
   v
CERTIFY
   |
   v
LEARN
```

---

# 41. Repository Navigation

```text
CallingGraph-Unfolding-for-AI-Coding/
│
├── README.md
│
├── START-HERE.md              <-- You are here
├── CONTENTS.md
│
├── CGU-001-CallingGraph-Unfolding.md
├── CGU-002-Two-Phase-Search-to-Trigger-Localized-Unfolding.md
├── CGU-003-Design-Time-CallingGraph.md
├── CGU-004-The-Unfolding-Gap.md
├── CGU-005-Differential-Unfolding-and-Certification.md
├── CGU-006-CallingGraph-as-AI-Coding-Control-Plane.md
│
├── docs/
│   ├── FIGURE-INDEX.md
│   ├── GLOSSARY.md
│   └── FUTURE-DIRECTIONS.md
│
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

# 42. Recommended First Reading Session

A practical first session is:

```text
START-HERE.md
      |
      v
Fig-000
      |
      v
CGU-001
      |
      v
Fig-003
      |
      v
CGU-003
      |
      v
Fig-005
      |
      v
CGU-004
      |
      v
CGU-006
```

This route gives the fastest path from the basic concept to the full AI Coding architecture.

Then read:

```text
CGU-002
CGU-005
```

for deeper algorithmic lineage and certification theory.

---

# 43. Current Scope Boundary

CGU v1.0 studies:

$$
\boxed{
Function\text{-}Only\ CallingGraph\ Unfolding
}
$$

Included:

* functions;
* calling relations;
* calling paths;
* functional localization;
* functional unfolding;
* Design-Time vs Realized structure;
* structural differences;
* structural certification evidence.

Not yet formally included:

* Condition;
* Runtime State;
* Data semantics;
* Time;
* Probability;
* Policy semantics;
* complete behavioral equivalence.

This boundary is deliberate.

---

# 44. What Comes Next?

The theoretical framework now suggests several engineering steps.

A minimal CGU implementation could demonstrate:

```text
1. Define DT-CG
2. Select Trigger
3. Localize Subgraph
4. Unfold Functional Paths
5. Dispatch Coding Task
6. Generate / Provide Implementation
7. Extract RT-CG
8. Compute Delta-CG
9. Perform Differential Unfolding
10. Generate Certification Report
```

Such an MVP would convert the current theoretical framework into an executable research platform.

---

# 45. The Research Door Opened by CGU

The immediate research question is CallingGraph Unfolding.

But the larger question is:

> **What happens when software structure becomes an active computational object that participates in planning, generation, validation, and learning?**

That question reaches beyond conventional CallingGraph analysis.

It points toward:

$$
\boxed{
Structural\ AI\ Coding
}
$$

and potentially toward:

$$
\boxed{
Structural\ Control\ Infrastructure
\ for\ Autonomous\ Software\ Engineering
}
$$

---

# 46. Final Map

If the entire repository must be compressed into one diagram, use this:

```text
                    INTENT
                       |
                       v
                DESIGN-TIME CG
                       |
                       v
                    UNFOLD
                       |
                       v
             STRUCTURAL WARGAMING
                       |
                       v
                    DISPATCH
                       |
                       v
                  AI CODING
                       |
                       v
                    PROGRAM
                       |
                       v
                     FOLD
                       |
                       v
                 REALIZED CG
                       |
              +--------+--------+
              |                 |
              v                 v
           DELTA-CG      DIFFERENTIAL
                          UNFOLDING
                              |
                              v
                           DELTA-U
                              |
                              v
                     RUNTIME EVIDENCE
                              |
                              v
                       CERTIFICATION
                              |
                 +------------+------------+
                 |            |            |
                 v            v            v
              ACCEPT        REPAIR       REPLAN
                                            |
                                            v
                                          LEARN
                                            |
                                            v
                                      BETTER DT-CG
```

---

# 47. Final Takeaway

CallingGraph Unfolding begins with a simple structural observation:

$$
Program
\rightarrow
CallingGraph
$$

is only one direction.

Once the CallingGraph is treated as an operational structural object, another direction becomes possible:

$$
CallingGraph
\rightarrow
LocalizedFunctionalPossibility
$$

That second direction enables Design-Time CallingGraphs.

Design-Time CallingGraphs enable structural planning.

Structural planning enables localized AI coding and dispatch.

Folding generated code back into a Realized CallingGraph enables comparison.

Differential Unfolding exposes hidden structural gaps.

Runtime evidence strengthens validation.

Certification converts that evidence into an explicit assurance claim.

Learning feeds the result back into future designs.

The complete loop is:

$$
\boxed{
Design
\rightarrow
Unfold
\rightarrow
Dispatch
\rightarrow
Generate
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

And the central architectural principle is:

$$
\boxed{
\text{Move AI Coding Control Upstream—from Token Generation to Structural Planning.}
}
$$

---

## Continue Reading

Start with:

**`CGU-001-CallingGraph-Unfolding.md`**

Then continue through:

```text
CGU-001
   ↓
CGU-002
   ↓
CGU-003
   ↓
CGU-004
   ↓
CGU-005
   ↓
CGU-006
```

---

**CGU — CallingGraph Unfolding**

> **Fold Structure. Localize Relevance. Unfold Possibility.**

> **Design the Structure Before Generating the Code.**

> **Certify the Evidence, Not Just the Similarity.**

> **Design. Unfold. Dispatch. Generate. Fold. Compare. Certify. Learn.**
