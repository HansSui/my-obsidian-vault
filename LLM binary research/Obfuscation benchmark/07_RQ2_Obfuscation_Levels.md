# BinDeObfBench: RQ2 — Obfuscation Intensity Levels

## Setup
- Levels **LV-1 → LV-6** (LV-6 = all 6 techniques combined)
- Non-LLM baselines excluded (poor scalability)

---

## Key Finding
**Non-linear degradation**: Rapid lexical decline; semantic metrics more stable.

---

## Semantic Preservation by Level

| Model | LV-1 | LV-6 | Drop |
|-------|------|------|------|
| **ChatDEOB** | 78.24% | 58.30% | −19.94% |
| **ReCopilot** | 74.18% | 54.62% | −19.56% |
| **DeepSeek-R1** | — | **62.89%** | **Smallest drop** |

> **Brittleness of standard SFT** under compounded transformations.
> **Reasoning models maintain stronger semantic preservation** → gap widens with complexity.

---

## Lexical vs. Semantic

| Metric | Trend |
|--------|-------|
| **Lexical (BLEU)** | Sharp decline with intensity |
| **Semantic** | Relatively stable |

**Interpretation**: LLMs prioritize **functional reconstruction > syntactic restoration**.

---

## Code Simplicity

| Model Type | Behavior |
|------------|----------|
| **Standard models** | Inflated complexity (repetitive, low-entropy fragments) |
| **Reasoning models** | Leverage deduction to **refactor logic, reduce complexity** |

---

## Conclusion
> **Reasoning models excel at high obfuscation intensity**; domain expertise alone only helps at mild levels.