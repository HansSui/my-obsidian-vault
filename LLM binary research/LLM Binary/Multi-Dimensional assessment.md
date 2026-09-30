## Previous studies rely on limited metrics $\to$ Challenge to full-on assessment.
## Therefore they've created multi-dimensional evaluation.
---
## With quality across 4 domains:
* ### Lexical consistency
* ### Semantic preservation
* ### Code simplicity
* ### Code readability
---
### Lexical consistency: 
* #### A direct measure of how the recovered code matches the unobfuscated one.
* #### Alignment at the textual level (identifier naming, function signatures and syntactic structure)
* #### BLEU score : n-gram overlap (deobfuscated and the reference pseudocode).
---
### Semantic preservation:
* #### Using Dual-perspective Semantic Fusion method
 ![[Alg1 Dual-perspective semantic.png]]
* #### Capture implicit semantics by using Qwen2.5-Coder-1.5B- Instruct
   * #### Extract explicit semantic features that are resilent to obfuscation and calculate Jaccard similarity.
   * #### We then integrate implicit and explicit score through a linear fusion strat (weighting by coefficient $a$).
   * #### Using 2 metrics :ROC- AUC, PR-AUC
	   * #### ROC: Assess the global discriminative ability.
	   * #### PR: Evaluates the robutness of positive identification.
	![[figure3 Grid search for alpha.png]]
---
### Code Simplicity:
* #### Token-wise delta entropy: Capture the incremental contribution of each token to the sequence's information complexity.
* #### Evalute in such platform:
	* #### Unobfuscated
	* #### Obfuscated
	* #### Deobfuscated
		#### $\to$ Measure the restoration of code simplicity.
![[math1.png]]
#### Where P:
![[math2.png]]
#### To calculate:
![[math3.png]]
#### If it reduces, successful mitigation of obfuscated-induced complexity.
---
### Code readability:
* #### Halstead complexity: cognitive effort to comprehend software based on:
	* #### The count
	* #### Diversity 
		#### Of its operators and operands.
* #### Volume measures the information content.
* #### Difficulty reflects cognitive complexity.
* #### Effort required for review and moditification. $\leftarrow$ main focus.
