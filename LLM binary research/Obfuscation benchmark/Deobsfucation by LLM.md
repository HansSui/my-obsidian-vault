## A set of task-oriented prompts for better in-context learning
* ### Prompt Engineering: 2 strategies
	* #### Zero - shot: providing task description and target obfuscated pseudocode. But its limitation listed in Challenge C3 $\to$ struggle to complex pattern. 
		#### $\to$ Introduction of few-shot.
	* #### Few - shot: Augments the prompt with demonstration examples.
### $\to$ Effective for adapting LLM to specialized domains.
### $\to$ Few-shot raised comparable performance while lower computational overhead.
---
## LLMs Selection
### 5 distinct groups : 
* #### General-purpose
* #### Code-specific
* #### Reasoning-optimized
* #### Domain-specific expert
* #### Task-specific
![[table4 Summary of BCDM.png]]
#### The implementation of chatDEOB differs from the paper (GPT-3.5-Turo as the backbone in paper). But we use Qwen2.5-Coder-7B-Instruct.
* #### Prioritize open-source model to avoid:
	* #### High cost
	* #### Accessibility limiations (those with closed-source)
* #### Comparison of domain-specific and task-specific $\to$ ReCopilot to make comparison.
#### Use their methodology $\to$ So that it's different from their benchmark.
---
### Non-LLM Deobfuscation methods
#### We have made significant strides in this domain. However, these remain closed-source.
#### $\to$ Such RE LLMs like Xyntia and QSynthesis are not suitable for benchmark.
* #### Xyntia: limited to processing code snippets and can't handle functions.
* #### QSynthesis: need the manual identification.
### $\to$ D810 and GooMBA (2 main focus)
* #### D810: 
	* #### Hex-Rays microcode pipeline.
	* #### Backward variables tracing.
	* #### Simulated execution and pattern matching.
		#### $\to$ Reconstruct obfuscated code and retrieve semantics.
* #### GooMBA:
	* #### Tree traveral.
	* #### Algebraic simplification.
	* #### Heuretic evaluation and SMT solver verification.
		#### $\to$ Simplify Mixed boolean-Arithmetic expressions with guaranteed semantics.
