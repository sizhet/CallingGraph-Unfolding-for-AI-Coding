# CGU-001 — CallingGraph Unfolding

## From Folded Program Structure to Localized Functional Possibility

**Project:** CallingGraph Unfolding for AI Coding
**Series:** CGU — CallingGraph Unfolding
**Document:** CGU-001
**Status:** Foundational Paper
**Scope:** Function-Only CallingGraph
**Version:** v1.0

---

## Abstract

A CallingGraph is commonly treated as a structural representation extracted from an existing program: nodes represent callable functional units, edges represent calling relations, and calling paths reveal possible chains of functional execution.

This paper proposes a broader interpretation.

A CallingGraph can be understood as a **folded representation of program functionality**. It compresses a potentially large set of functional execution possibilities into a reusable structural form. Once such a structure exists, it can also support the opposite computational direction: **CallingGraph Unfolding**.

CallingGraph Unfolding is not the exact inverse of CallingGraph Folding. It does not reconstruct the original source code, nor does it enumerate the entire program universe. Instead, a trigger, task, or structural localization condition activates a relevant region of the folded graph and expands it into a **localized functional possibility space**.

The resulting structural pattern is:

$$
\text{Program}
\rightarrow
\text{CallingGraph}
\rightarrow
\text{Localized Functional Possibility}
$$

or more generally:

$$
\text{Folding}
\rightarrow
\text{Localization}
\rightarrow
\text{Unfolding}
$$

This shift changes the role of the CallingGraph. It is no longer only a post-hoc visualization or analysis artifact. It can become an active structural object for reasoning, planning, AI coding, runtime validation, and eventually structural certification.

This first paper deliberately restricts the theory to the **Function dimension** of CallingGraphs. Conditions, runtime states, policies, and richer structural dimensions are important future directions, but they are kept outside the core model in order to establish a minimal and operational foundation for CallingGraph Unfolding.

---

# 1. Introduction

Programs contain enormous amounts of structural information.

Source code explicitly describes functions, methods, classes, branches, data operations, interfaces, and runtime behavior. Yet much of this information can be reorganized into more compact structural representations.

One particularly useful representation is the **CallingGraph**.

At its simplest:

$$
CG=(V,E)
$$

where:

* \(V\) is a set of callable functional units;
* \(E\) is a set of calling relations.

A calling path can be represented as:

$$
P:
v_0
\rightarrow
v_1
\rightarrow
\cdots
\rightarrow
v_n
$$

This representation is usually interpreted in one direction:

$$
\text{Program}
\rightarrow
\text{CallingGraph}
$$

That direction is important.

But it is only half of the story.

If a CallingGraph captures and compresses functional structure from a program, then an important question follows:

> **Can the folded functional structure be selectively unfolded again?**

The answer proposed in this paper is yes.

However, the result is not necessarily the original program.

Instead:

$$
CG
\xrightarrow{\text{Unfolding}}
\mathcal{U}_{F}
$$

where \(\mathcal{U}_{F}\) represents a localized space of functional possibilities that can be exposed from the CallingGraph under a particular trigger, task, or structural focus.

This process is called:

> **CallingGraph Unfolding**

---

# 2. CallingGraph as Functional Folding

Consider a software system containing thousands of source-code statements.

At the source-code level, the system may appear as a large universe:

$$
\mathcal{P}
=
\{
statement_1,
statement_2,
\dots,
statement_n
\}
$$

Yet much of its functional organization may be represented more compactly as:

```text
RequestHandler
      |
      v
Authentication
      |
      v
Validation
      |
      v
BusinessService
      |
      v
Persistence
```

The CallingGraph does not preserve every source-code detail.

Instead, it preserves selected structural relations.

We therefore define a functional Folding operation:

$$
F_{CG}:
Program
\rightarrow
CG_F
$$

where:

$$
CG_F=(V_F,E_F)
$$

and the subscript \(F\) emphasizes that this first model concerns only the **Function dimension**.

The Folding operation removes or hides many details while preserving functional topology.

Conceptually:

$$
\text{Large Program Structure}
\xrightarrow{\text{Folding}}
\text{Compact Functional Structure}
$$

This gives the CallingGraph an important interpretation:

> **A CallingGraph is a folded functional representation of a program.**

---

# 3. Folding Is Selective Structural Compression

CallingGraph Folding should not be confused with ordinary file compression.

The purpose is not byte reduction.

It is **structural compression**.

Suppose a program contains:

```text
Controller
  -> Validator
  -> Service
  -> Repository
  -> Database
```

Each unit may contain hundreds or thousands of source-code tokens.

The CallingGraph folds those details into a smaller structural description:

$$
Controller
\rightarrow
Validator
\rightarrow
Service
\rightarrow
Repository
\rightarrow
Database
$$

The graph preserves one class of information:

$$
\text{Functional Calling Topology}
$$

while suppressing many others.

Therefore:

$$
F_{CG}(Program)
\neq
Program
$$

and generally:

$$
|CG|
\ll
|Program|
$$

when measured in representational complexity.

But the reduced structure remains computationally meaningful.

That retained structural meaning is what makes Unfolding possible.

---

# 4. From Folding to Unfolding

If Folding produces:

$$
Program
\xrightarrow{F_{CG}}
CG
$$

a naive interpretation of Unfolding might be:

$$
CG
\xrightarrow{F_{CG}^{-1}}
Program
$$

This paper explicitly rejects that interpretation.

CallingGraph Unfolding is generally **not an inverse function**.

We therefore write:

$$
\boxed{
U_{CG}
\neq
F_{CG}^{-1}
}
$$

The CallingGraph normally does not contain enough information to reconstruct the exact original program.

Different implementations may share similar CallingGraphs.

For example:

```text
A -> B -> C
```

may correspond to many different source-code implementations.

Therefore:

$$
CG
\not\Rightarrow
Unique\ Program
$$

Instead, the CallingGraph defines or constrains a space of functional possibilities.

Thus:

$$
CG
\xrightarrow{U_{CG}}
\mathcal{P}_{CG}
$$

where:

$$
\mathcal{P}_{CG}
$$

is a functional possibility space compatible with the folded structure.

This is the first essential distinction of CallingGraph Unfolding:

> **Unfolding recovers structural possibilities, not necessarily the original representation.**

---

# 5. CallingGraph Unfolding

We define **CallingGraph Unfolding** as:

> **The selective expansion of a folded CallingGraph into a localized set of functional structures, calling paths, or functional possibilities relevant to a trigger, task, or structural focus.**

In minimal form:

$$
U:
(CG,t)
\rightarrow
\mathcal{U}
$$

where:

* \(CG\) is the folded CallingGraph;
* \(t\) is a trigger;
* \(\mathcal{U}\) is the resulting unfolded functional structure.

A more explicit expression is:

$$
\mathcal{U}_{F}(CG,t)
\subseteq
\mathcal{P}_{F}(CG)
$$

where:

$$
\mathcal{P}_{F}(CG)
$$

denotes the full functional possibility space represented or permitted by the CallingGraph.

Thus, Unfolding is normally selective.

It does not require:

$$
U(CG)=Entire\ Graph
$$

Instead:

$$
U(CG,t)=Relevant\ Functional\ Region
$$

This property is central to the computational usefulness of CallingGraph Unfolding.

---

# 6. Trigger-Localized Unfolding

The central mechanism is:

$$
\boxed{
Trigger
\rightarrow
Localization
\rightarrow
Unfolding
}
$$

Suppose the folded CallingGraph contains:

```text
                         Payment
                            |
             +--------------+--------------+
             |              |              |
             v              v              v
       Validation       Authorization     Logging
             |              |
             v              v
       RiskCheck        Transaction
                            |
                    +-------+-------+
                    |               |
                    v               v
                  Commit         Rollback
```

A task concerning transaction rollback should not require full expansion of the entire graph.

Instead:

```text
Trigger:
"Investigate transaction rollback"
```

may produce:

```text
Payment
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

The trigger identifies a structural hotspot.

The hotspot defines a localized region.

The localized region is then unfolded.

Therefore:

$$
CG
\xrightarrow{t}
CG_{local}
\xrightarrow{U}
\mathcal{U}_{local}
$$

This is **Trigger-Localized Unfolding**.

---

# 7. Hotspot Unfolding

CallingGraph Unfolding can therefore be understood as a form of **Hotspot Unfolding**.

The computational pattern is not:

```text
Search Everything
       |
       v
Inspect Everything
       |
       v
Select Something
```

Instead:

```text
Folded CallingGraph
        |
      Trigger
        |
        v
Structural Hotspot
        |
        v
Localized Unfolding
        |
        v
Reason / Plan / Execute
```

This suggests an important computational objective:

$$
Cost(U)
\propto
|\mathcal{U}_{local}|
$$

rather than:

$$
Cost(U)
\propto
|\mathcal{P}_{universe}|
$$

The exact complexity depends on the Unfolding algorithm and graph representation, but the architectural principle is clear:

> **Do not repeatedly search the full universe when a folded structure can localize the relevant functional region first.**

---

# 8. CallingGraph as a Functional Possibility Structure

The conventional view is:

> CallingGraph = description of what calls what.

The Unfolding view is broader:

> CallingGraph = folded structure from which functional possibilities can be selectively exposed.

Consider:

```text
A
|
+----> B ----> D
|
+----> C ----> E
```

This graph contains several possible calling paths:

$$
P_1=A\rightarrow B\rightarrow D
$$

$$
P_2=A\rightarrow C\rightarrow E
$$

and potentially localized subpaths such as:

$$
P_3=B\rightarrow D
$$

The CallingGraph therefore contains more than a static picture.

It implicitly contains a structured path space:

$$
\mathcal{P}(CG)
=
\{
P_1,P_2,\dots,P_n
\}
$$

A trigger can activate a subset:

$$
T
\rightarrow
\mathcal{P}_{local}
\subseteq
\mathcal{P}(CG)
$$

This motivates a stronger interpretation:

> **A CallingGraph is a compressed generator of functional structural possibilities.**

---

# 9. CallingGraph Unfolding Space

We introduce the concept:

> **CallingGraph Unfolding Space**

For the Function-only model:

$$
\boxed{
\mathcal{U}_{F}(CG,t)
}
$$

denotes the functional structures that become relevant or reachable under trigger \(t\).

At this stage, the model deliberately avoids adding condition, state, policy, probability, or temporal dimensions.

Therefore:

$$
\mathcal{U}_{F}
$$

is strictly a **functional structural space**.

Possible elements include:

* calling paths;
* reachable functional regions;
* upstream callers;
* downstream callees;
* alternative branches;
* functional neighborhoods;
* local subgraphs;
* dependency chains;
* structural alternatives.

The concept provides a foundation for later algorithmic work without prematurely increasing dimensional complexity.

---

# 10. Folding and Unfolding Are Asymmetric

A critical property of the model is asymmetry.

Suppose:

$$
F_{CG}(Program)=CG
$$

The Folding operation intentionally removes information.

Therefore:

$$
Information(CG)
<
Information(Program)
$$

in the general case.

Consequently:

$$
U(CG)
$$

cannot normally reconstruct all information removed during Folding.

Instead:

$$
Program
\xrightarrow{F}
CG
\xrightarrow{U}
Structural\ Possibility
$$

The second object may resemble some structures of the first program, but:

$$
U(F(Program))
\neq
Program
$$

in general.

A more useful interpretation is:

$$
U(F(Program),t)
\approx
Relevant\ Functional\ Structure(Program,t)
$$

The purpose of Unfolding is therefore not perfect reconstruction.

Its purpose is **useful structural recovery and expansion**.

---

# 11. Unfolding Is Not Full Enumeration

Another important boundary is:

$$
Unfolding
\neq
Enumerating\ All\ Paths
$$

For a large graph, complete path enumeration may be combinatorially expensive or even operationally meaningless.

CallingGraph Unfolding instead emphasizes:

$$
\boxed{
Selective\ Structural\ Expansion
}
$$

The desired process is:

$$
Trigger
\rightarrow
Localization
\rightarrow
Bounded\ Expansion
$$

Possible bounding mechanisms include:

* maximum depth;
* maximum number of nodes;
* target function;
* direction of traversal;
* path relevance;
* task scope;
* structural stopping rules.

Therefore a practical Unfolding engine should support:

$$
U(CG,t,b)
$$

where \(b\) represents a structural bound.

This distinction is essential for scalable AI coding applications.

---

# 12. CallingGraph Unfolding and LLM Unfolding

Large Language Models provide a useful conceptual comparison.

An LLM can be viewed as a deeply folded representation of linguistic and learned statistical structure.

A prompt activates a localized generation process:

$$
LLM
+
Prompt
\rightarrow
Localized\ Generation
$$

The complete learned structure is not explicitly unfolded.

Only a contextually activated portion becomes visible through generation.

CallingGraph Unfolding exhibits a related structural pattern:

$$
CallingGraph
+
Trigger
\rightarrow
Localized\ Functional\ Expansion
$$

The two systems are fundamentally different in representation and computation.

Nevertheless, both illustrate a broader principle:

$$
\boxed{
Folded\ Structure
+
Trigger
\rightarrow
Localized\ Unfolding
}
$$

This principle deserves study independently of either LLMs or CallingGraphs.

---

# 13. A Critical Difference from LLMs

The comparison should not erase an important difference.

LLM internal structure is generally high-dimensional, distributed, and difficult to interpret directly.

CallingGraphs are comparatively explicit.

Nodes and edges can often be inspected, traced, modified, constrained, and audited.

Therefore CallingGraph Unfolding may offer properties that are difficult to obtain from purely latent model representations:

* explicit structural localization;
* inspectable paths;
* controllable boundaries;
* reproducible traversal;
* structural comparison;
* human-readable evidence;
* machine-verifiable constraints.

This gives CallingGraph Unfolding particular importance for software engineering and AI coding.

---

# 14. From Analysis Artifact to Active Structural Object

Traditionally:

$$
Program
\rightarrow
CallingGraph
\rightarrow
Analysis
$$

The CallingGraph is downstream of the program.

CallingGraph Unfolding suggests another direction:

$$
CallingGraph
\rightarrow
Structural\ Reasoning
$$

and eventually:

$$
CallingGraph
\rightarrow
Planning
\rightarrow
Coding
$$

Thus, the CallingGraph can move from:

> **Passive structural artifact**

toward:

> **Active structural object**

This transition is fundamental.

A passive graph tells us what structure exists.

An active CallingGraph can help determine:

* which region matters;
* which path should be inspected;
* which functional unit should be generated;
* which task should be dispatched;
* which structural alternatives should be compared;
* which implementation should later be validated.

This paper establishes only the Unfolding foundation.

Later papers in this series develop these implications.

---

# 15. The Design-Time Direction

Once CallingGraph Unfolding is admitted, a natural reversal becomes possible.

For existing software:

$$
Program
\xrightarrow{Folding}
CallingGraph
$$

For software not yet written:

$$
Intent
\rightarrow
Design\text{-}Time\ CallingGraph
\xrightarrow{Unfolding}
Program\ Possibility\ Space
$$

This leads to the concept of:

> **Design-Time CallingGraph (DT-CG)**

A Design-Time CallingGraph describes:

> **What the future software should structurally become before implementation is complete.**

This idea is developed formally in CGU-003.

For the present paper, the important consequence is simply:

$$
\boxed{
CallingGraph\ Unfolding
\text{ allows CallingGraphs to operate upstream of code.}
}
$$

That changes their architectural role.

---

# 16. A Minimal Canonical Pipeline

The minimal CGU pipeline is:

```text
Program
   |
   | Folding
   v
CallingGraph
   |
   | Trigger
   v
Localization
   |
   | Unfolding
   v
Functional Possibility
```

For AI coding, the direction can later become:

```text
Intent
   |
   v
Design-Time CallingGraph
   |
   | Unfolding
   v
Localized Coding Structure
   |
   v
AI Coding
   |
   v
Program
   |
   | Folding
   v
Runtime / Realized CallingGraph
```

Together:

$$
\boxed{
Intent
\rightarrow
DT\text{-}CG
\rightarrow
Unfold
\rightarrow
Code
\rightarrow
RT\text{-}CG
}
$$

This pipeline becomes the foundation for structural comparison and certification.

---

# 17. Why CallingGraph Match Is Not Enough

The Unfolding interpretation immediately raises a validation problem.

Suppose two programs produce structurally similar CallingGraphs:

$$
CG_A
\approx
CG_B
$$

It does not automatically follow that all relevant functional expansions are equivalent.

In general:

$$
CG_A
\approx
CG_B
\not\Rightarrow
U(CG_A,t)
=
U(CG_B,t)
$$

for every relevant trigger \(t\).

This observation leads to the concept of the:

> **Unfolding Gap**

which will be developed in CGU-004.

The consequence for AI coding certification is significant:

$$
Static\ CG\ Match
\neq
Complete\ Runtime\ Proof
$$

Instead, CallingGraph similarity becomes one class of structural evidence within a larger certification framework.

---

# 18. Structural Evidence Rather Than Universal Proof

CallingGraph analysis can provide strong evidence.

For example:

* expected nodes exist;
* expected edges exist;
* forbidden calls are absent;
* required calling paths exist;
* local structures match;
* selected unfolding paths are consistent.

But unless the relevant system is sufficiently constrained for complete formal verification, these observations do not imply universal behavioral equivalence.

Therefore:

$$
\boxed{
CallingGraph\ Evidence
\neq
Universal\ Boolean\ Proof
}
$$

This does not weaken the value of CallingGraphs.

It clarifies their correct role.

They provide **structural evidence**.

Unfolding expands the scope and depth of that evidence.

Runtime validation can add further evidence.

Together, these can support:

$$
\boxed{
Evidence\text{-}Bounded\ Certification\ Confidence
}
$$

This topic is developed in CGU-005.

---

# 19. Scope Boundary: Function Only

Calling structures can clearly contain more information than function topology.

Potential future dimensions include:

$$
F = Function
$$

$$
C = Condition / Context
$$

$$
S = State
$$

and possible projection or policy operators:

$$
P = Projection / Policy
$$

A richer future model might therefore investigate:

$$
F
\rightarrow
F+C
\rightarrow
F+C+S
$$

However, this paper deliberately restricts the initial theory to:

$$
\boxed{
F = Function\ Only
}
$$

The reasons are methodological.

First, Function-only CallingGraphs already provide a large and useful structural space.

Second, the foundational meaning of Folding and Unfolding should be established before additional dimensions are introduced.

Third, excessive dimensional expansion risks turning CallingGraph theory into an overly broad representation framework before its core computational mechanisms are understood.

Therefore:

> **CGU v1.0 begins with Function-only CallingGraph Unfolding.**

Richer Calling Structural Spaces remain an explicit future research direction.

---

# 20. Research Questions

The Function-only model already raises substantial research questions.

### RQ-1 — What exactly should be preserved during CallingGraph Folding?

Possible answers include:

* direct calling relations;
* transitive calling relations;
* path topology;
* functional hierarchy;
* functional boundaries;
* reusable structural motifs.

---

### RQ-2 — What constitutes a valid Unfolding trigger?

Examples may include:

* target function;
* coding task;
* bug location;
* feature request;
* structural gap;
* verification target;
* dependency question.

---

### RQ-3 — How should localization be performed?

Possible mechanisms include:

$$
Target
\rightarrow
Neighborhood
$$

$$
Target
\rightarrow
Upstream\ Callers
$$

$$
Target
\rightarrow
Downstream\ Callees
$$

or:

$$
Task
\rightarrow
Candidate\ Functional\ Region
$$

---

### RQ-4 — How should Unfolding be bounded?

Potential bounds include:

* depth;
* width;
* path count;
* node count;
* target completion;
* structural relevance;
* stopping conditions.

---

### RQ-5 — How should Unfolding quality be measured?

Potential measures include:

* coverage;
* precision;
* localization quality;
* structural relevance;
* runtime agreement;
* downstream coding success.

---

### RQ-6 — How should multiple possible Unfoldings be compared?

If:

$$
U_1(CG,t)
\neq
U_2(CG,t)
$$

we need methods for:

* ranking;
* A/B comparison;
* structural scoring;
* runtime validation;
* confidence estimation.

---

### RQ-7 — How can CallingGraph Unfolding guide AI coding?

This includes:

* task decomposition;
* structural planning;
* agent dispatch;
* local code generation;
* repair;
* structural verification.

---

### RQ-8 — How can Unfolding evidence contribute to certification?

This requires distinguishing:

$$
CG\ Match
$$

from:

$$
Unfolding\ Match
$$

and ultimately from:

$$
Runtime\ Behavioral\ Evidence
$$

---

# 21. Toward a General Unfolding Model

Although this project begins with CallingGraphs, the underlying structural form may be more general:

$$
\boxed{
Folded\ Structure
+
Trigger
\rightarrow
Localized\ Unfolding
}
$$

This pattern may appear in:

* language models;
* calling graphs;
* decision structures;
* routing structures;
* knowledge structures;
* behavioral structures;
* runtime structures.

The CallingGraph provides a particularly useful research object because its structure is explicit enough to inspect and manipulate while still rich enough to represent nontrivial software organization.

Therefore CGU may serve both as:

1. a practical AI coding framework; and
2. a concrete laboratory for studying structural Folding and Unfolding more generally.

---

# 22. Canonical Statements

The foundational claims of this paper can be summarized in three statements.

### Canonical Statement I

> **A CallingGraph is not only a folded representation of existing software; it can also serve as a generative structural skeleton for future software.**

### Canonical Statement II

> **CallingGraph Unfolding is the trigger-localized expansion of folded functional structure into a bounded functional possibility space.**

### Canonical Statement III

> **Unfolding is not inverse reconstruction: its purpose is to recover useful structural possibilities rather than reproduce the original program exactly.**

---

# 23. The Foundational Transition

The conventional CallingGraph lifecycle is:

$$
Program
\rightarrow
CallingGraph
\rightarrow
Analysis
$$

The CGU lifecycle begins to look like:

$$
CallingGraph
\rightarrow
Localization
\rightarrow
Unfolding
\rightarrow
Reasoning
$$

and eventually:

$$
Intent
\rightarrow
CallingGraph
\rightarrow
AI\ Coding
\rightarrow
Program
\rightarrow
CallingGraph
$$

Therefore the deeper transition proposed by this work is:

$$
\boxed{
CallingGraph:
\quad
Post\text{-}hoc\ Program\ Representation
\quad\Longrightarrow\quad
Design\text{-}Time\ and\ Runtime\ Structural\ Control
}
$$

CallingGraph Unfolding provides the missing computational direction required for this transition.

---

# 24. Conclusion

CallingGraphs have traditionally been used to describe, inspect, and analyze the functional structure of existing software.

This paper proposes that they can play a broader role.

A CallingGraph can be interpreted as a **folded functional structure**.

Because the folded structure retains meaningful calling topology, it can be selectively expanded through **CallingGraph Unfolding**.

The central pipeline is:

$$
\boxed{
Program
\rightarrow
CallingGraph
\rightarrow
Localization
\rightarrow
Unfolding
\rightarrow
Functional\ Possibility
}
$$

The process is asymmetric:

$$
U
\neq
F^{-1}
$$

and selective:

$$
U(CG,t)
\subseteq
\mathcal{P}(CG)
$$

Its objective is not complete reconstruction or exhaustive search.

Its objective is:

> **localized recovery and expansion of useful functional structure.**

This interpretation transforms the CallingGraph from a passive artifact into a potentially active computational structure.

It creates a path toward:

* Design-Time CallingGraphs;
* structural simulation before coding;
* localized AI coding;
* structural task dispatch;
* differential unfolding;
* runtime validation;
* confidence-based certification;
* structural learning.

The first step, however, should remain deliberately simple:

$$
\boxed{
F = Function\ Only
}
$$

By first understanding how functional CallingGraphs fold, localize, and unfold, richer dimensions can later be explored without sacrificing conceptual clarity.

The foundational research question is therefore:

> **If a CallingGraph is a folded functional representation of software, how much useful software structure can be recovered, generated, localized, and controlled through its unfolding?**

That question defines the starting point of CallingGraph Unfolding.

---

## Next in the CGU Series

**CGU-002 — From Two-Phase Search to Trigger-Localized Unfolding**

The next paper studies the structural lineage:

$$
\text{Full-Universe Search}
\rightarrow
\text{Two-Phase Search}
\rightarrow
\text{Structural Localization}
\rightarrow
\text{Trigger-Localized Unfolding}
$$

and examines why Two-Phase Search provides an important explicit structural predecessor to both LLM-style and CallingGraph-style Unfolding.

---

## Scope Note

This document establishes the **Function-only foundation** of CallingGraph Unfolding.

The following extensions are intentionally deferred:

* Condition / Context dimensions;
* Runtime State dimensions;
* Policy / Projection operators;
* probabilistic CallingGraphs;
* temporal CallingGraphs;
* richer Calling Structural Spaces.

These extensions should be investigated only after the Function-only CGU model is sufficiently defined, implemented, and experimentally evaluated.

---

**CGU Principle**

$$
\boxed{
\text{Fold Structure. Localize Relevance. Unfold Possibility.}
}
$$
