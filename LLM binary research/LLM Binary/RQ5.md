## Deobfuscation on binary malware
### We construct a high-quality evalution dataset of malicious binaries.
### Using LLMs (CodeLlama and DeepSeek-R1) and Non-LLM deobfuscation.
![[Pasted image 20260929211644.png]]

---
## Non-LLM (D810 and GooMBA) sucks if facing realistic malware (which has higher entropy and complexity).
### The contrast say it's better generalization fr:
* ### Better code readability by reducing Halstead complexity.
* ### Effectively simplifies deceptive control-flow.
* ### Tho struggles to maintain semantic preservation.
	* ### $\to$ Intro to ChatDEOB (supervised fine-tuning).
	* #### (The highest semantic preservation and lowest entropy).

---
## Result
#### Reasoning models offer better readability but task-specific fine-tuning is better for computational logic of real-life malware.
