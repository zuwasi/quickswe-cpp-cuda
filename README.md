# QuickSWE v2 — C++ & CUDA Benchmark

**Amp Deep³ vs Claude Opus 4.7** — AI Coding Agent Benchmark on C++ and CUDA tasks.

## Results (April 17, 2026)

| Metric | Amp Deep³ | Claude Opus 4.7 |
|--------|-----------|------------------|
| **Overall** | **97.6%** (40/41) | 82.9% (34/41) |
| **C++** | **100%** (22/22) | 90.9% (20/22) |
| **CUDA** | **94.7%** (18/19) | 73.7% (14/19) |
| **Regressions** | 1 | 3 |

📊 **[Live Dashboard](https://zuwasi.github.io/Public-html-pages/amp-deep3-vs-claude-opus47-benchmark.html)**

## Task Structure

Each task has:
- `description.md` — bug description and expected behavior
- `src/` — source code with deliberate bugs
- `tests/` — pytest-based test harness (compiles and runs C++/CUDA)
- `metadata.json` — task metadata (language, difficulty, category)

### C++ Tasks (task_051 – task_075)
25 tasks covering: circular buffers, hash maps, red-black trees, B+ trees, coroutine schedulers, SIMD operations, and more.

### CUDA Tasks (task_076 – task_100)
25 tasks covering: vector operations, parallel reduction, sparse matrix ops, bitonic sort, cooperative groups, tensor cores, dynamic parallelism, FFT, ray tracing, and molecular dynamics.

### Difficulty Levels
- 🟢 **Easy** — basic indexing/logic bugs
- 🟡 **Medium** — template metaprogramming, reference counting, warp shuffles
- 🟠 **Hard** — red-black trees, cooperative groups, tensor cores
- 🔴 **Extreme** — coroutine schedulers, persistent data structures, BFS warp-centric

## Running the Benchmark

```bash
# On WSL2 with CUDA toolkit installed
export PATH=/usr/local/cuda/bin:$PATH
python3 runner.py --agent deep3-vs-opus47 --timeout 600
```

### Agent Options
- `amp` — Amp standard mode
- `amp-deep3` — Amp Deep³ (xhigh reasoning)
- `claude` — Claude Code (default model)
- `claude-opus-4-7` — Claude Code with Opus 4.7
- `deep3-vs-opus47` — head-to-head comparison

## Environment
- WSL2 Ubuntu 24.04
- g++ 13.3.0, CUDA 12.8, Python 3.12
- NVIDIA GPU with compute capability 7.5+

## License
MIT
