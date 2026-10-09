# BinDeObfBench: Implementation Design

## Dataset Construction

### Data Source & Granularity

| Aspect | Choice | Rationale |
|--------|--------|-----------|
| **Object** | Source → executable pipeline | Multi-layered obfuscation at each phase |
| **Granularity** | File-level (not repo-level) | Avoids cross-file dependencies, compilation errors, resource issues; better semantic validity |
| **Sources** | CodeNet, HumanEval, EvalPlus | Broad algorithmic diversity, logical complexity |

### Data Filtering (3 Issues → 3 Solutions)

| Issue | Solution | Effect |
|-------|----------|--------|
| Extreme length variations | **Token Length Constraint**: 256–8000 tokens | Retains 95% data, preserves validity |
| Compilation failures | **Compilation Validity Check**: Keep only successful compiles | Ensures executable ground truth |
| Data redundancy | **Redundancy Elimination**: Single representative per problem | Removes duplicates |

---

## Obfuscation Techniques (6 Mainstream)

| Category | Technique | Description |
|----------|-----------|-------------|
| **Control Flow** | **Bogus Control Flow (BCF)** | Add conditional branches, loops, jumps |
| **Control Flow** | **Control Flow Flattening (FLA)** | Central dispatcher/loop flattens structure |
| **Control Flow** | **Opaque Predicate (OPQ)** | Constant conditions mislead branch analysis |
| **Expression** | **Instruction Substitution (IS)** | Replace ops with arithmetic/logic equivalents |
| **Expression** | **Mixed Boolean-Arithmetic (MBA)** | Combine Boolean + arithmetic ops |
| **Expression** | **ImmediateMove (IMV)** | Decompose direct assignment into steps |

**Tools used**: OLLVM, Hikari, Tigress, Alcatraz (open + commercial)

---

## Transformation Combinations

- **Composite obfuscation** > isolated techniques
- Levels **LV-1 → LV-6** (LV-6 = all 6 techniques)
- Each obfuscator = independent tool
- **4 ISAs**: ARM, MIPS, x86, x64
- **4 Optimization levels**: O0–O3
- Symbols/debug info stripped → realistic RE scenarios

![Obfuscation Transformations](picture/Table1%20obfuscation%20transform.png)

---

## Validity Verification (Two-Stage Pipeline)

1. **String matching** → filter ineffective transformations
2. **GPT-4o as automated verifier** → 95.2% accuracy, Fleiss' κ = 0.83 (3 RE experts)

![LLM Models Employed](picture/table3%20LLM%20models%20employed.png)

> **Conservative bias**: Rejects valid samples rarely misclassifies invalid → desirable for gatekeeping.

![Pilot Study Results](picture/table2%20Pilot%20study.png)

**Sample format**: `<original pseudocode, obfuscation type, obfuscated pseudocode>`

---

## Malware Dataset

- **Sources**: theZoo, MalwareSourceCode (open-source repos)
- **Purpose**: Evaluate LLM deobfuscation under realistic threat conditions