## Only using x64-architecture at O0 optimization level.
### Result: Depends less on the number of raw parameters and more on the synergy of reasoning capability and domain-specific expertise.
![[figure4 performanceof diff O-L.png]]

## The question: The overall performance of LLMs in binary code deobfuscation.
### Strong internal reasion mechanisms LLMs (DeepSeek-R1 and OpenAI-o1) outperform when handling high-entropy obfuscated code.
#### $\to$ Mostly for control-flow-intensive transformations (like FLA).
--- 

### Report:
#### ==DeepSeek-R1== :  Lexical consistency gain of 18.89%. a 3.95% improvement in semantic preservation and Halstead complexity low.
#### $\to$ Absolute best performance in general-purpose / code-sepcific on the FLA transformation.
#### $\to$ Reasoning-oriented inference, exemplified by the test-time scaling paradigim, supports progressive output and refinement during inteference.
#### $\to$ Multiple reasoning steps rather than single-pass generation.

#### ==General-purpose models== has a degrading performance under complex obfuscation like 5.31% drop in lexical consistency.
#### $\to$ The limitations of direct non-reasoning when facing control-flow and logic dependencies.

---
### Challenge:
#### The applicability of traditional scaling laws to binary code analysis.
* #### parameter count does not guarantee better performance.
* #### Domain-specific expertise outweights.
#### $\to$ Code specific models outperforms general-purposes models.
#### Because it recogizes and preserves code structure and control-flow semantics $\gt$ unstructured or noisy text.
#### ==32B Qwen2.5-Coder:==
* #### 16.14% increase in lexical consistency on the BCF transformation. $\gt$ 70B Llama-3.1.
* #### Pre-training aligned with program analysis $\gt$ model scale alone.
#### ==General-purpose:==
* #### GPT-4o generates more simplified code through "destructive writing" $\to$ semantic fidelity.
#### Fine-tune baseline ChatDEOB $\gt$ the domain-pretrained Recopilot.
#### $\to$ Task-specific SFT $\gt$ broad domain pre-training.
##### (Where it's better in mapping obfuscated and deobfuscated code representations.)
--- 
### Non- LLM deobfuscation methods suck
#### D810 and GooMBA can restore the original code within their operational scopes. 
#### HOWEVER, rule-based approaches exhibit ==2 limitations:==
* #### Rely on fixed pattern-matching rules $\gt$ flexible semantic rewriting.
* #### Syntatically dense ouputs with limited readability improvement.
#### $\to$ LLMs offer superior readability improvement.
