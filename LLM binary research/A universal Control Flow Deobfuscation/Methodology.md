---
aliases:
  - the methodology of the solution of two above problem
tags:
  - deobfuscation
  - paper
  - program-analysis
date_read: 2026-10-14
status: 50%
---
## Overview
**From how control flow obfuscation can ==Inflate path complexity==
$\to$ The birth of ==LUCID framework ==(To solve two key problems).
- **The framework scheme works as three-lay cascades:
	- **Binary $\to$ ==intermediate representation (IR) layer.==
	- ==**RFPS generation module== $\to$ recover the execution paths.
	- **Control flow graph is reconstructed via ==TFPS merge module==, fed back to decomposition process.
---
## RFPS generator
### Problem faces
- **2 approaches:
	- **1. Path constraint solving: enumerates TFPS paths via SMT solver (verify RFPS membership).
	- **2. Input space sampling: collect execution paths via feeding diverse inputs.
- **Problems:
	- **1. Opaque predicates, non-linear conditions and path explosion.
	- **2. Vast input space and incomplete coverage.
### Solution
>Focus on program's jump relationships.

**Decision function $J_b$: $$H_b \times D \to S_b \text{ depends on } H_b$$
which depends on the sequence of blocks started to b & input d.
Since $TFPS$ independent to input space $D$ $\to$
$$J_b(S_b | H_{b,d} \in D) \text{ merged all d in D under historical path }H_b$$
$$\to \phi_b(S_b|H_b) = \cup_{d \in D}\{J_b(s_b|H_b,d)\}$$
As $\phi$ an input-independent  superset filter that map $P_tfps$ to $P_rfps$.

**For a given $P = (b)$, decision function $J_{b}$ of basic block $b$ $\to$ The reachable successor set $S(b)$.
$$(\pi = \{b_1,b_2,...,b_n\} \in P_{tfps}) \notin P_{rfps} \iff \text{a basic block } b_{k+1} \notin S(b_k)$$
Other words decision function $Jb$ can filter $P_{tfps} \text{ to } P_{rfps}$.

**For now $\phi$ remains ==unsolvable== since its input space consists of RFPS.
Therefore, all possible $H$ are partitioned into equivalence classes based on result $S$.
Partition: $$
\forall h1,h2 \in H,F(h_1) = F(h_1) \to S(h_1) = S(h_2)
$$
Called ==Condition prefixes== and with the exists of set of reachable successors called ==predicate mapping rule==. Where ==worst case==, condition prefixes will traverse the RFPS from start to block b.




