---
title: The introduction/abstract of the paper
tags:
  - paper
  - deobfuscation
  - llm
  - program-analysis
  - cfg
date_read: 2026-10-06
status: completed
alias:
  - LUCID
---
---
## The use of Code obfuscation
- ***Uses*: For codebase protection like IP protection or malicious code protection by hackers.
	$\to$ Making it the complex version  - by making it *Difficult*. 
- ***Major focus*: Complicating the program's control flow structure.
- ***Skill includes*: Opaque predicates (OP), control-flow flattening (CFF) & BCF.
	$\to$ Interfere with static analysis, reduce readability.
$\to$ Essential for binary analysis & downstream applications.
---
## Struggling deobfuscation tools:
- ***Problems*: Struggle to provide generic deobfuscation - Only within their scopes (any states-of-the-art algo they fail miserably).
- ***Good News*: More methods like
	- *Sympolic execution* (SE)
	- *Abstract interpretation* (AI)
	- *Program synthesis* (PS)
	- *SMT solvers* (SMT)
- ***Bad News:* Lack of generality
	-** **SE & AI*: Handling data-flow obfuscations (limited effectiveness beyond scope).
	- ***AI*: Handling the continuous evolution of OP.
	- ***SMT*: Can detect false path vs sensitive out-of-distribution code 
		- **Like pointer aliasing & MBA expression. 
		- **Ineffective against CFF.
---
## LLM & LUCID to code deobfuscation.
### Comparison

| Metric / Aspect | Existing LLM Methods | LUCID |
| :--- | :--- | :--- |
| **Approach** | Direct code generation | Intervenes during decompilation |
| **Functional Equivalence** | Hard to ensure / verify | Preserved (compilable output) |
| **Control Flow** | Drastically altered | Reconstructs clean, explicit CFG |
| **Hallucination** | Frequent issue | Mitigated via heuristic guidance |
| **Theory** | Lacks solid framework | Formalizes deobfuscation goals |

---

### Evaluation Summary

* **Baselines**: Rule-based scripts, LLVM `opt`, program synthesis, direct LLMs
* **Target Obfuscators**: Tigress, OLLVM, Polaris (13 techniques)
* **Results**:
  * Cyclomatic complexity reduced by **52.2%**
  * Complete deobfuscation on **53.8%** of samples
  * Suppressed **>99%** of bogus path inflation
---
## Contribution:
- **==*Formalization of Control flow Task & Metrics*==: 
	- Guild the integration of LLM.
	- Evaluate both code obfuscation & performance of the models.
- **==*Novel Framework with controllable LLM intervention*:==
	- **Leverage linear-time LLM access
	$\to$ *Derive mapping rules* & guild non-linear execution.
	- **Reconstruct concise control flow graphs.
	$\to$ Controllable and trustworthy intervention of LLM.
	- **Adapting to diverse obfuscation techniques based on:
		- **Intrinsic semantics
		- **Mitigating hallucination risks
-  ***Comprehensive validation & Benchmark*:
	- **Comparison of our model with other up-to-date obfuscation tools available.
	- ***Tools:* Script-based, LLM Q&A-based, optimized compilation-based & program synthesis-based solutions,
	$\to$ *Advantages* in static deobfuscation analysis.
---
