# BinDeObfBench — Master Index

## Paper: *BinDeObfBench: A Comprehensive Benchmark for Binary Code Deobfuscation with LLMs*

---

## Document Map

| # | File | Description |
|---|------|-------------|
| **00** | [[00_Introduction]] | Problem motivation, benchmark overview, 5 key findings |
| **01** | [[01_Overview]] | Challenges (C1–C3) & Solutions (S1–S3), metrics table |
| **02** | [[02_Background]] | Formal problem definition, related work gaps |
| **03** | [[03_Implementation_Design]] | Dataset construction, 6 obfuscation techniques, LV-1–6, verification, malware data |
| **04** | [[04_Multi_Dimensional_Assessment]] | 4 evaluation dimensions: Lexical, Semantic, Simplicity, Readability |
| **05** | [[05_Deobfuscation_by_LLM]] | Prompt strategies, 5 LLM groups, non-LLM baselines (D810, GooMBA) |
| **05b** | [[05b_Evaluation_Setup]] | Hardware, runtime, RQ index |
| **06** | [[06_RQ1_Overall_Performance]] | Overall results: reasoning + code-specific > scale |
| **07** | [[07_RQ2_Obfuscation_Levels]] | Non-linear degradation; reasoning wins at high intensity |
| **08** | [[08_RQ3_Compilation_Environments]] | ISA (CISC vs RISC) & optimization (O0–O3) effects |
| **09** | [[09_RQ4_In_Context_Learning]] | Few-shot helps pattern-matchers, hurts reasoners |
| **10** | [[10_RQ5_Malware_Generalization]] | Real malware: task-SFT > reasoning for semantics; reasoning > SFT for readability |
| **11** | [[11_Discussion]] | Code properties, lessons, threats to validity, future work |

---

## Quick Reference: Key Takeaways

| Question | Answer |
|----------|--------|
| **What model type wins overall?** | Reasoning-optimized (DeepSeek-R1) + code-specific (Qwen2.5-Coder) |
| **Does scale matter?** | No — 32B code-specific > 70B general; task-SFT > domain pre-training |
| **Obfuscation intensity?** | Reasoning models degrade least; standard SFT brittle |
| **ISA / Opt level?** | Reasoning models architecture-agnostic; refactor O3 complexity |
| **Few-shot?** | Helps CodeLlama; hurts DeepSeek-R1 (disrupts reasoning) |
| **Real malware?** | ChatDEOB (task-SFT) best semantics; DeepSeek-R1 best readability |

---

## Metrics Cheatsheet

| Dimension | Metric | Better = |
|-----------|--------|----------|
| Lexical Consistency | BLEU | ↑ Higher |
| Semantic Preservation | ROC-AUC, PR-AUC | ↑ Higher |
| Code Simplicity | Token-wise Delta Entropy | ↓ Lower |
| Code Readability | Halstead Effort | ↓ Lower |

---

## Obfuscation Techniques (6)

| Abbr | Name | Type |
|------|------|------|
| **BCF** | Bogus Control Flow | Control Flow |
| **FLA** | Control Flow Flattening | Control Flow |
| **OPQ** | Opaque Predicate | Control Flow |
| **IS** | Instruction Substitution | Expression |
| **MBA** | Mixed Boolean-Arithmetic | Expression |
| **IMV** | ImmediateMove | Expression |

**Levels**: LV-1 (single) → LV-6 (all combined)

---

## Model Groups Evaluated

| Group | Representative Models |
|-------|----------------------|
| General-purpose | GPT-4o, Llama-3.1 |
| Code-specific | CodeLlama, Qwen2.5-Coder |
| Reasoning-optimized | DeepSeek-R1, OpenAI-o1 |
| Domain-specific | ReCopilot |
| Task-specific | ChatDEOB (SFT) |

---

*Generated from BinDeObfBench paper notes — restructured for clarity & navigation.*