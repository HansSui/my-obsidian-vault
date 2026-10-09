# BinDeObfBench: Introduction

## Why Obfuscation Matters

Obfuscation applies semantics-preserving transformations to increase structural complexity, hindering reverse engineering (RE). Common techniques:

![LLM obfuscation example](picture/LLM%20obfuscation%20example.png)

| Technique | Purpose |
|-----------|---------|
| **Omitted Variables** | Hide/conceal data |
| **Control Flow Flattening** | Overcomplicate simple functions via central dispatcher |
| **Instruction Substitution** | Replace simple math with complex equivalent operations |
| **Bogus Control Flow** | Add misleading branches/loops/jumps |

**Result**: Increased program complexity → hindered semantic understanding.

**Limitation of traditional approaches**: Tailored to specific obfuscation patterns → limited generalizability, poor adaptability to diverse schemes.

---

## Why LLMs for Deobfuscation?

LLMs show strong capability in:
- Code generation
- Automatic repair
- Code completion
- Binary analysis

**Critical gap**: No systematic evaluation of LLM performance on binary deobfuscation. We don't know which LLM types excel.

---

## BinDeObfBench: The Benchmark

- **Scale**: 2,108,736 obfuscated programs with ground truth
- **Pipeline**: 6 transformations across 3 compilation stages (pre-compilation, compile-time, post-compilation)
- **Models evaluated**:
  - General-purpose / code-specific
  - Reasoning-optimized
  - Domain-specific (binary analysis)

---

## Key Empirical Findings (5)

1. **Traditional scaling assumption challenged**: Fine-tuning > broad domain pre-training
2. **Obfuscation intensity matters**: As intensity ↑, reasoning capability > domain expertise
3. **ISA & optimization levels**: Impact performance significantly
4. **In-context learning**: Standard models > reasoning models for ICL adaptation
5. **Generalization**: Deobfuscation capabilities transfer to complex malicious binaries