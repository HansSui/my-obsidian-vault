### Obfuscation is widely needed in semantics-preserving transformations to increase structural complexity.
### It is needed to apply multiple techniques in RE. 

![[Pasted image 20260924095933.png]]
#### Examples of how obfuscation works
### The underlying steps in this specific obfuscation:

* #### Omitted Variables : Which hides and conceal the hidden data.
* #### Control flow flattening : Using obfuscation techniques to overcomplicate simple function
* #### Instruction Substitution : Works of simple mathematical operation to harden value ouput compution.
* #### Bogus Control flow: much harder to analyze if-statement.
### $\rightarrow$ Increase program complexity and hinder semantic understanding.
### However, it's tailored to specific obfuscation pattern $\rightarrow$ limited generalizability and poor adaptability to diverse scheme.

---
## Introduction to LLM
### Strong capability in code generation, automatic repair and code completion with very impressive binary analysis.
### 1 weakness tho? It's the ==lack of systematic evaluation of the performance==. We don't know which type of LLM is the best in binary-analysis.

## $\to$ Introduction to BinDeObfBench
### It's the benchmark where it makes comparison to several LLM models of deobsfucation capabilities. Which uses ==2,108,736 obfuscated programs with ground truth==.
### With the flow consists of 6 transformation where   ==3 main stages sit (pre, time, post compilation).==
### The set of LLM the benchmark used to evaluate:
* ### General purposes / code-specific
* ### Reasoning model
* ### Tailored for binary analysis task.

---
# Identification
### 5 empirical findings:
* ### Tradition scaling assumption. Where fine-tuning $\gt$ broad domain pre-training.
* ### Obfuscation intensity increases, reasoning $\gt$ domain expertise.
* ### ISAs and optimization levels increases its performance.
* ### In-context learning proves much better where standard models $\gt$ reasoning.
* ### Deobfuscation capabilities can generalize effectively to more complex malicious binary scenarios.