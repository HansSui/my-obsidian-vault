## Dataset construction
### Data Source Selection and Granularity: 
* #### ==The main objects==:  
	* ##### Analyze the generation pipeline from source code TO executable binaries.
	* ##### Different obfuscation transformation can be introduced at each phase $\to$ multi-layered obfuscation strategies.
* #### ==Data granularity==: 
	* ##### file- level source code $\gt$ repositories-level project. Due to the fact that inherent complexity of repo-level (cross-file dependency and directory hierachies)
		##### $\to$ Technical challenges, high resource consumption and dependency conflicts. 
		##### $\to$ Therefore, they introduce uncontrollable compilation errors.
	* ##### file-level offers better semantic validity and controllability
* #### $\to$ Flexible application of different strategies, better experimental operability and reproducibility.
### Data source:
* #### CodeNet dataset, a curated and famous benchmark.
* #### LLM evaluation like HumanEval and EvalPlus $\to$ programming challenge dataset.
#### $\to$ A broad spectrum of algo types, capturing logical complexity and diversity enough.
### Data filtering
### Since raw data from CodeNet may contain ==noise which restrain the evaluation validity==.
### $\to$ Therefore we separate into ==3 primary issues==:
* #### Extreme length variations.
* #### Compilation failures.
* #### Data redundancy.
### With each issues we introduce assigned solutions:
* #### ==Token Length Constraint==: Retain token within (256 $\to$ 8000) $\to$ improve 95% of the data while still stay data validity of the entire source code.
* #### ==Compilation Validity Check==: Only samples that compile successfully.
* #### ==Redundancy Elimination==: Deduplicate the dataset by selecting single representative solution for each problem.
---
## Obsfucation technique:
### We using: OLLVM, Hikari, Tigress and Alcatraz (both open-source and commercial tools).
###  From this, we restrict to ==6 mainstream techniques== where covering form-base (expression) and structural (control flow) techniques.

* #### ==Bogus Control flow== : Additional conditional branches, loops or jump statement.
* #### ==Instruction substitution==: Replace instructions with arithmetics, logical or data movement operations.
* #### ==Control flow flattening==: flattened structure using central dispatcher or loop.
* #### ==Mixed boolean-arithmetic expression==: Combine Boolean logic and arithmetic operations. 
* #### ==Opaque Predicate==: Embeds conditions where evaluations' reach a constant, misleading branches.
* #### ==ImmediateMove==: Decompose a direct assignment into multiple steps.
---
### Transformation Combinations
#### Using composite obfuscation $\gt$ isolated techniques. Which ranging from LV-1 to LV-6 (consists of all techniques above).
![[Table1 obfuscation transform.png]]
##### (Each designated obfuscators serve as an individual tools to obfuscate).
#### The model has been optimized with 4 ISAs (ARM, MIPS, x86,x64) and 4 other optimization options (O0 $\to$ O3).
#### $\to$ Removing symbols and debug information to better RE scenarios.
---
### Validity Verification and sampling
#### Two stage verification pipeline:
* ##### String matching to filter ineffective transformations.
* ##### Utilizd GPT-4o as an automated verifier.
![[table3 LLM models employed.png]]
##### Each sample has an identification with the format:              ==<original pseudocode, obfuscation type, obfuscated pseudocode>.==
---
### The use of Pilot Study
#### 3 RE experts assesed the sample, yielding Fleiss' kappa of 0.83 $\to$ perfect agreement.
#### GPT-4o achieved an overall accuracy of 95.2%.
#### The studies show a conservative bias where the model rejects valid one but rarely misclassifies the invalid one.
#### $\to$ This attribution is desireable therefore take this as a gatekeeper for data construction.
![[table2 Pilot study.png]]

---
### Malware dataset
#### To evaluate the LLM obfuscation capabilities within realistic threat scenarios $\to$ uisng these open-source repos like theZoo / MalwareSourceCode to better approximate realistic attack conditions.

# [[Deobsfucation by LLM]]
# [[Multi-Dimensional assessment]]
