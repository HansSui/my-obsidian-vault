## Performance under different obfuscation levels
### (The non-LLMs proves to be sucked, they are excluded from the evaluation)
---
## The result:
### A non-linear degradation where rapid lexical declines.
### mild obfuscation: Reasoning degradation offers limited advantages.
#### Where ChatDEOB, its semantic preservation score of 78.24% at L-1 but 58.3% at L-6.
#### ReCopilot: 74.18% in capturing pseudocode distribution. But it dropped to 54.62% at L-6.

#### $\to$ Brittleness of standard SFT $\gt$ compounded transformations.
#### BUT, reasoning models like DeepSeek-R1 remain stronger in semantic preservation (62.89%). This furthers the gap when handling complex obfuscated logic.
---
## Lexical/ semantic metrics 
### Lexical low, semantic stable.
### $\to$ LLMs prioritize functional equivalence as they treat:
* ### Functional reconstruction $\gt$ syntactic restoration.
## Code simplicity
### Standard models exhibits inflated complexity (repetitive, low-entropy fragments).
### However, reasoning models leverage deductive capabilities to:
* #### Refractor logic.
* #### Reduce overall complexity.
#### $\to$ Simplify high-entropy logic effectively.
---
### CONCLUSION: reasoning models better domain expertise (excel at only mild obfuscation).
