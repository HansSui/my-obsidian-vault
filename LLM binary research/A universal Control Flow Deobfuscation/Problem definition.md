---
title: Problem definition
tags:
  - paper
  - deobfuscation
status: 50%
---
## How the math states:
$$CFG  = (V,E)$$ **This is a control flow graph where it consists:
$$P_{tfps}$$ Which is Topologically Feasible path set: control-flow graph's topology.
$$Prfps$$
Which is Runtime feasible path set: paths executed under concrete runtime condition.
$\to$ A well-programmed program has its $P_{tfps}$ as close as $P_{rfps}$.

---
## The idea:
Altering the V and E $\to$ Making $P_{tfps} (obfs)$'s path not in $P_{rfps}(obfs)$.

---
## Goals:
Reconstructing a minimal topological path set $P_{tfps}(optim)$ from $CFG_{obf}$ such that $P_{rfps}$ is preserve (in $P_{tfps}$).

---
## Topology
- **Cyclic graphs, both $P_{rfps}$ and $P_{tfps}$ are infinite in size. So it's never a case where u calculate directly.
- **Construct finite $P_{rfps}$: Limit loops or the execution time.
![[Fig1.png]]

**Basically, each SCC holds x kinds of basic cycles $\to$ Represented as linear combinations.
## Von Neumann ordinal definition
- **Using the smallest infinite ordinal $w$ where k $\in w$  $\exists$ (class of subsets of paths). 
* **Each subset has paths with exactly k cycles, for each cycle has $x$ possible type choises. 
* **Total number of paths: $x^{n}$ where $n$ is finite number of cycles.
---
## Algorithm: Calculate $P_{tfps}(CFG)$ 
$$|P_{tfps}(CFG)| = \sum_{\pi \in P_{CAG}(entry,end)}(\prod_{v \in \pi}(a_{v} \times B^{w}_{v}) $$
Where $P_{CAG}(entry,end)$ is the set of paths from entry to end in the CAG(Cycle aggregation graph).
$\pi= \{v_{1},...,v_{k}\}$ represents a path in $P_{CAG}(entry,end)$.
for each supernode $v$:
$$a_{v} = |P_{simple}(v_{in},v_{out})|$$
$$
\beta_v = 
\begin{cases} 1 & \text{if $SCC_v$ is acylic },\\ |e-n+p|& \text{otherwise}. \end{cases}
$$
Where $e,n,p$ represent edge, node and connected components (p=1 for SCCs).

---
## Limitation
**Control flow-pertubing obfuscation techniques:
$\to$ Constitute a subset of all obfuscation method.
Sovled? 
$\to$ Formal model for $P_{tfps}$ size provides  rigorous means to quantify the impact by altering path complexity.
- **BCF: artificial branches $\to$ increasing path complexity linearly via $a_v$ term.
- **CFF: $N$ basic blocks into a single SCC, elevating the $B_v$ parameter from 1 to $N$ .
