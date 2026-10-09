# BinDeObfBench: Discussion

## Impact of Code Properties

### Code Length (LOC)

| Category            | Count | Observation                                                                     |
| ------------------- | ----- | ------------------------------------------------------------------------------- |
| **Short** (1–50)    | 564   | Baseline                                                                        |
| **Medium** (50–200) | 1,342 | —                                                                               |
| **Long** (>200)     | 1,094 | Halstead ↑; **DeepSeek-R1 handles best** — maintains high semantic preservation |

### Symbolic Information

| Setting | Finding |
|---------|---------|
| **Stripped** | Lexical consistency > non-stripped (standardized vars align with ground truth) |
| **Non-stripped** | Variable names help logic deduction |
| **Semantic preservation** | Negligible loss when stripped removed |

> **Deduce logic from execution patterns > variable names**

---

## Lessons Learned & Implications

1. **Multi-dimensional evaluation is essential** — no single metric suffices (lexical, semantic, simplicity, readability)
2. **LLMs excel at semantic paraphrasing** — generate clean, readable code
3. **Performance enhancers** (ranked):
   - Step-by-step reasoning
   - Code-specific training
   - Binary domain knowledge
   - In-context learning

---

## Threats to Validity

| Type | Concern |
|------|---------|
| **External** | Covers common obfuscators; not exhaustive (future obfuscators may differ) |
| **Internal** | Limited open-source non-LLM baselines; fine-tuning data differences shift performance |
| **Construct** | Automated metrics are effective proxies but don't fully capture human cognitive load |

---

## Future Work
- Expand obfuscator coverage
- Human study for readability validation
- Hybrid reasoning + SFT approaches for malware
- Cross-architecture generalization at higher optimization levels