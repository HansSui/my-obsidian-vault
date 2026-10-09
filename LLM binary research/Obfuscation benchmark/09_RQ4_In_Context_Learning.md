# BinDeObfBench: RQ4 — In-Context Learning (Few-Shot) Impact

## Setup
- **Demonstrations**: Source code + 6 obfuscation transformations → high-quality references
- **Models**: CodeLlama + DeepSeek-R1
- **Shots**: 0 → few (progressive)

![In-Context Learning Results](picture/table7%20In-context%20learning.png)

---

## Code Complexity (Halstead / Delta Entropy)
- **Both models excel**: Rapid Halstead reduction, stable delta entropy
- **Less dependent on demonstrations** — inherent simplification capability

---

## Semantic Preservation (Divergent Trajectories)

| Model | Few-Shot Effect | Interpretation |
|-------|-----------------|----------------|
| **CodeLlama** | **Positive correlation** — more context → higher semantic accuracy | Better pattern matching from examples |
| **DeepSeek-R1** | **Diminishing returns** — high lexical but semantic drops | Few-shot prompts induce **surface-level imitation** of simplified style, disrupting internal reasoning steps |

---

## Key Insight
> **Few-shot helps pattern-matchers (CodeLlama) but can hurt reasoners (DeepSeek-R1)** by overriding multi-step reasoning with shallow style mimicry.

---

## Practical Implication
| Model Type | Recommendation |
|------------|----------------|
| Standard / code-specific | Use few-shot for semantic gains |
| Reasoning-optimized | Zero-shot often better; few-shot risks reasoning disruption |