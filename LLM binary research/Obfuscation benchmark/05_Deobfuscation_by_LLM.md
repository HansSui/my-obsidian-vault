# BinDeObfBench: Deobfuscation by LLM

## Prompt Engineering Strategies

| Strategy | Description | Trade-off |
|----------|-------------|-----------|
| **Zero-shot** | Task description + target obfuscated pseudocode | Struggles with complex patterns (Challenge C3) |
| **Few-shot** | Adds demonstration examples | Comparable performance, lower compute overhead; effective for domain adaptation |

---

## LLM Selection (5 Groups)

| Group | Examples | Purpose |
|-------|----------|---------|
| **General-purpose** | GPT-4o, Llama-3.1 | Baseline broad capability |
| **Code-specific** | CodeLlama, Qwen2.5-Coder | Code-oriented pre-training |
| **Reasoning-optimized** | DeepSeek-R1, OpenAI-o1 | Test-time scaling, multi-step reasoning |
| **Domain-specific expert** | ReCopilot | Broad binary code pre-training |
| **Task-specific** | ChatDEOB | SFT for deobfuscation |

![BCDM Summary](picture/table4%20Summary%20of%20BCDM.png)

> **Implementation note**: Paper used GPT-3.5-Turbo for ChatDEOB; this benchmark uses **Qwen2.5-Coder-7B-Instruct** (open-source priority: cost, accessibility).

---

## Non-LLM Deobfuscation Baselines

| Method | Approach | Limitation |
|--------|----------|------------|
| **Xyntia** | Pattern-based synthesis | Snippet-only; no function-level |
| **QSynthesis** | Program synthesis + SMT | Requires manual pattern identification |
| **D810** | Hex-Rays microcode + backward tracing + simulated execution + pattern matching | Rule-based; syntactically dense output |
| **GooMBA** | Tree traversal + algebraic simplification + SMT verification | MBA-specific; limited readability gains |

**Benchmark focus**: **D810** and **GooMBA** (most relevant/representative)