## Problem definition
### We got $S$ and $C_{S \to I}$ transform to IR $I$, and $C_{I \to B}$ generate the binary code B, with a sequential pipeline where transformation $T$ can be applied at the source, IR, binary stages. 

$$S^{'} = O_{S}(S,T_{S})$$ $$I^{'} = O(C_{S \to I}(S^{'},T_I)$$ $$B^{'} = O_B(C_{I \to B}(I^{'}), T_B)$$
### The mapping of some stages can be unobfuscated where final stage is $B_{obj} = B{'}$ equivalent to the original program B.
### RE where $P^{''} = D(P^{'})$ $\to$ Ensure that $P^{''}$ is sementically equivalent to the original P.

### The object here is to focus deeply on decompiled stage rather than disassembled stage.

---
# Related work:
### METAMORPHASM framework for using generative capacity of LLMs.
### Multi-dimensional framwork to assess deobfuscation performance.
### ChatDEOB, accurately reconstruct code by using Mixed Boolean-arithmetic and Control flow flattening.

### However, limited in scope and do not provide rigorous evaluation across diverse obfuscation.

