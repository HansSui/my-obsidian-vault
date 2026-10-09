---
title: How does one create the foundation
date_read: 2026-10-09
tags:
  - paper
  - deobfuscation
---
## Control flow obfuscation
- ### *Masking program's true execution paths*.
- ### 3 Development directions:
	- **==*False execution path injection*==: Direct control-flow branches to false execution. Using *Nop* & *Reusing existing code snippets*.
	$\to$ *Evolve into* MBA expression $\to$ High adversarial opaque predicates.
	- **==*Decoulping execution from storage order*==: Separates physical vs execution sequences $\to$ Undermine readability with many techniques:
	**$Including:$(control-flow flattening, basic block splitting, loop unrolling, code randomization and code virtualization).
	- **==*Combined obfuscation*== (GuiDiv for entropy-based evaluation, knapsack algorithm for intensity and cost).
## Advances in NLP for code deobfuscation.
- **==*Improved the ability of LLMs to understand and generate code*==: focused on high-level languages vs proven effective for lower-level (LLVM IR and assembly code).
- ***Error*: Binary still remains more challenging which reveals high error rates in direct code generation.
- ***Fundamental limitation*: frequent absence of safeguards (original & model-generated) $\to$ ==*Overreliance*== on parameter tuning & ==*unrealistic expectation*== $\to$ Worsen by model illusion. 
- **Remain open challenges despite efforts in improving, required manual verification that negates automation benefits.
