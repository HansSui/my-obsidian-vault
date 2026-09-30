## Impact of code properties
### Code length (line of Code/ LOC)
* ### Obfuscated function is categorized into 3:
	* #### Short (1-50) - counts 564
	* #### Medium (50-200) - counts 1342
	* #### Long ($\gt$ 200) - counts 1094 
		#### $\to$ As it's getting longer, halstead higher, Deepseek treats this better while maintains high semantic preservation
### Sympolic information: 2 categories (non-stripped/ stripped)
* #### Deduce program logic from execution patter $\gt$ variable or names.
* #### Removing sympose $\to$ negligible loss in semantic preservation.	
* #### Stripped's lexical consistency $\gt$ non-stripped
#### $\to$ Generate standardized variables align with ground truth than incorrect identifier guesses.
---
## Lesson learned & implications
### Multi-dimensional evaluation: Cannot be evaluated in one metric; 
#### $\to$ Required to go through lexcial consistency, semantic preservation, code simplicity and code readability.
### Semantic paraphrasing: LLMs excels at generating clean, readable code.
### Performance enhancers: Step-by-step reasoning, code-specific trainging, binary domain knowledge and in-context learning 
#### $\to$ Better performance boosting.
---
## Threat to validty
### External validity: Cover common obfuscator but not all of them in the future.
### Internal validity: Limited open-source, such non-LLMs with fine-tuning data $\to$ performance shifted.
### Construct validity: Automated metrics do prove effective proxies but not fully measure human cognitive load.

