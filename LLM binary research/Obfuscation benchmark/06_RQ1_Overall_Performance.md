# BinDeObfBench: RQ1 — Overall Performance

## Setup
- **Architecture**: x64 only
- **Optimization**: O0 only
- **Models**: All 5 groups (general, code-specific, reasoning, domain-expert, task-specific)

![Performance of Different Obfuscation Levels](picture/figure4%20performanceof%20diff%20O-L.png)

---

## Key Finding
**Performance depends less on parameter count, more on synergy of reasoning capability + domain expertise.**

---

## Results by Model Category

### 🏆 Reasoning Models (DeepSeek-R1, OpenAI-o1)
- **Excel at high-entropy obfuscated code**
- **Dominant on control-flow-intensive transforms (FLA)**
- **DeepSeek-R1 highlights**:
  - +18.89% lexical consistency (best on FLA)
  - +3.95% semantic preservation
  - Lowest Halstead complexity
  - **Test-time scaling**: Multi-step reasoning > single-pass generation

### Code-Specific Models (Qwen2.5-Coder-32B)
- **Outperforms larger general models** (e.g., > Llama-3.1-70B)
- +16.14% lexical consistency on BCF
- **Pre-training aligned with program analysis > model scale alone**

### General-Purpose Models (GPT-4o)
- **Degrading performance under complex obfuscation** (−5.31% lexical)
- "Destructive writing": Generates simplified code but loses semantic fidelity

### Domain vs. Task-Specific
- **ChatDEOB (SFT) > ReCopilot (domain pre-training)**
- Task-specific fine-tuning > broad domain pre-training
- Better at mapping obfuscated ↔ deobfuscated representations

---

## Non-LLM Baselines (D810, GooMBA)
| Limitation | Impact |
|------------|--------|
| Fixed pattern-matching rules | Inflexible vs. semantic rewriting |
| Syntactically dense output | Limited readability improvement |
| **LLMs offer superior readability** | — |

---

## Takeaway
> **Reasoning + code-specific training > raw scale**. Traditional scaling laws don't hold for binary analysis.