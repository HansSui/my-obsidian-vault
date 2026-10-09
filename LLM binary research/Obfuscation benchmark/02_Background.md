# BinDeObfBench: Background & Problem Definition

## Formal Problem Definition

Given:
- Source code $S$
- Compilation $C_{S \to I}$ → IR $I$
- Compilation $C_{I \to B}$ → Binary $B$

Obfuscation transformations $T$ applied at each stage:

$$
S' = O_S(S, T_S) \\
I' = O_I(C_{S \to I}(S'), T_I) \\
B' = O_B(C_{I \to B}(I'), T_B)
$$

**Goal**: Recover $B_{obj} = B'$ equivalent to original $B$.

Reverse engineering: $P'' = D(P')$ where $P''$ is semantically equivalent to original $P$.

**Focus**: Decompiled pseudocode (not disassembly) — higher-level semantics.

---

## Related Work & Gaps

| Work | Approach | Limitation |
|------|----------|------------|
| **METAMORPHASM** | LLM generative capacity | Limited scope |
| **Multi-dimensional framework** | Assessment metrics | Not rigorous across diverse obfuscation |
| **ChatDEOB** | MBA + CFF reconstruction | Narrow evaluation |
| **Xyntia / QSynthesis** | Rule-based (closed-source) | Snippet-only / manual identification needed |
| **D810 / GooMBA** | Non-LLM deobfuscation | Closed-source; not benchmark-suitable |

**Core gap**: No rigorous evaluation across diverse obfuscation schemes, ISAs, optimization levels.