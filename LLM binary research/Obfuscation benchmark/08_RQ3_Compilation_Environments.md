# BinDeObfBench: RQ3 — Compilation Environments (ISA & Optimization)

## Setup
- Models: **CodeLlama** (code-specific) + **DeepSeek-R1** (reasoning) — top performers from RQ1
- **4 ISAs**: ARM, MIPS, x86, x64
- **4 Opt levels**: O0, O1, O2, O3

![Performance Across Architectures](picture/figure5%20diff%20architecture.png)

---

## ISA Effects

| Model | Preference | Reason |
|-------|------------|--------|
| **CodeLlama** | **CISC (x64/x86) > RISC (ARM/MIPS)** | Training data predominantly x64/x86 → syntactic familiarity |
| **DeepSeek-R1** | **Architecture-agnostic** | Generalizes beyond ISA-specific patterns; handles verbose pseudocode |

> **Reasoning mitigates pre-training bias** across CISC/RISC.

---

## Optimization Level Effects

| Level | Effect on Pseudocode |
|-------|----------------------|
| O0 → O3 | Aggressive optimizations → convoluted logic, inlining, reordering |

| Model | O3 Behavior |
|-------|-------------|
| **CodeLlama** | Degrades significantly; mirrors input confusion |
| **DeepSeek-R1** | **Refactors convoluted logic → cleaner code** even at O3 |

---

## Summary

| Factor | CodeLlama | DeepSeek-R1 |
|--------|-----------|-------------|
| **ISA variance** | High sensitivity (CISC bias) | Robust |
| **Optimization (O3)** | Fails to simplify | **Excels at refactoring** |
| **Output style** | Verbose, mirrors obfuscation | Clean, readable |

---

## Answer
> **Reasoning capability bridges architecture gaps and refactors compiler-induced complexity** — standard models just reproduce the confusion.