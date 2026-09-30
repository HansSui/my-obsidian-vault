## Challenges
### C1: Lack realistic and diverse dataset
#### $\to$ We usually focus entirely on one limited dataset where it only affects on one singlar architecture. In reality, they focus on many deobsfucation techniques and some create self-obsfucational program to make it ZKP to attackers.

### C2: Absence of Comprehensive Metric for Deobsfucation Evaluation
#### $\to$ Only sementic correctness alone, this prevents holistic assessment of deobsfucation quality.
### C3: Knowledge gap caused by Distribution shift
#### $\to$ Obsfucation transformation introduce irregular control flows and high-entropy (create noises that are difficult to decipher) where mapping is challenging.
--- 
## Solution
### S1: A Large-scale and Diverse Obfuscation Evaluation Dataset
#### $\to$ Data set constructed from scratch where comprises diverse instruction set architectures, compilation settings and obsfucation transformations. 3 key stages: source code, immediate representation and binary.
---
### S2: Multi-dimensional Assessment metrics
#### $\to$ Using these metrics: lexical consistency, sementic preservation, code conciseness and readability.
 * #### BLEU for lexical where identifiers, keywords remain consistence.
 * #### Dual-Perspective Semantic Fusion method for semantic preservation to verify behavioral consistency.
 * #### Token-wise delta entropy for code conciseness which measures the token-level uncertainty.
 * #### Halstead Complexity to assess code readability which eliminates the cognitive effort.
![[figure2 Workflow.png]]
---
### S3: Bridging the knowledge gap of LLM
#### $\to$ Adopt in-context learning to mitigate the knowledge gap, better adapt to obsfucate binary. They introduce Recopilot, a pre-trained broad spectrum of binary code whereas ChatDEOB is for deobfuscation.

