## Impact of In-Context learning

### High-quality reference, we construct source code and then apply to 6 obfuscation transformations.
### Using CodeLlama and DeepSeek-R1.
![[Pasted image 20260929210404.png]]

---
## Report:
### Results demonstrate distinct performance trajectories as the shots increase.
### Code complexity: Both model excel, where healstead complexity is reduced rapidly and maintain delta entropy scores.
### $\to$ Better simplify code, eliminate obfuscation noise and less dependent on demonstrations.
---
### Semantic preservation:
* #### CodeLlama shows positive correlation between context availability and semantic accuracy. $\to$ Better pattern matching.
* #### DeepSeek-R1, diminishing semantic preservation despite high lexical consistency.
#### Few-shot prompts guild mimic the simplified style of the ref code, but for the reasonsing-enhanced model's internal reasoning steps. 
#### $\to$ Surface-level imitation $\gt$ deep semantic recovery.
