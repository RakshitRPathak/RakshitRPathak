### Hi, I'm Rakshit 👋

Final-year B.Tech (Computer Science & Business Systems) at **VIT Vellore**, graduating 2027. I build backend systems, ML pipelines with honest evaluation, and lately compilers and GPU kernels. **6 patent applications** (5 published), **3 papers submitted to IEEE Access**.

**Looking for:** a 6-month SDE internship, January to June 2027. Portfolio: **[rakshitrpathak.github.io](https://rakshitrpathak.github.io)**

---

#### Systems

| Project | What it is | Evidence |
|---|---|---|
| [**PTXForge**](https://github.com/RakshitRPathak/ptxforge) | MLIR/LLVM GPU kernel compiler for fused GEMM + bias + GELU: custom passes and a generated transform schedule lower it from linalg to PTX, plus a C++20 measurement-driven autotuner (cost model, roofline prior, ablated advisors) and a roofline studio. | Tuned kernel, 2048³ FP32: **85.6% of cuBLAS on a Tesla T4** (3,688.5 GFLOP/s, 1.78×) and **79.3% on a Blackwell RTX 5050 Laptop GPU** (7,546.6 GFLOP/s, 1.50×). The MLIR-generated kernel runs correctly on the RTX 5050 (3,008 GFLOP/s, no shared-memory staging yet). 10 FileCheck cases, 16 C++ unit tests |
| [**minic**](https://github.com/RakshitRPathak/minic) | A compiler in C++17: hand-written lexer, recursive-descent parser, semantic analysis, functions with call frames and recursion, bytecode generation with backpatching and a stack VM, plus an SSA IR over a control-flow graph with six optimization passes (constant propagation, global value numbering over the dominator tree, dead code elimination and more). | 119 checks: every program run on the bytecode VM and the SSA IR, optimized and unoptimized; a differential fuzzer in CI that caught 7 of 7 planted optimizer bugs; clean under ASan and UBSan |
| [**cuda-gpu-bench**](https://github.com/RakshitRPathak/cuda-gpu-bench) | CUDA kernels (naive vs tiled matmul, three reduction strategies) with a benchmark harness, PTX instruction analysis and a CPU emulator that runs the real kernels. | Measured on a Tesla T4 and an RTX 5050 Laptop GPU: `vec_add` at 257 / 272 GB/s; tiled matmul 1.53× / 1.27× the naive kernel (tiling is worth less with Blackwell's larger caches); warp-shuffle reduction 234 / 203 GB/s. 33 emulator checks |
| [**mini-kv-store**](https://github.com/RakshitRPathak/mini-kv-store) | Crash-safe LSM-tree key-value store in Java: write-ahead log with CRC and torn-tail truncation, memtable, SSTables with a sparse index and Bloom filters, k-way merge compaction, atomic MANIFEST. JDK only. | 39 tests including fault injection at every flush and compaction step; the tests were checked by deliberately planting bugs |
| [**system-design-primitives**](https://github.com/RakshitRPathak/system-design-primitives) | LRU, O(1) LFU, token bucket, sliding-window log and counter, consistent hashing with virtual nodes, Bloom filter. JDK only. | 32 tests |
| [**dsa-patterns**](https://github.com/RakshitRPathak/dsa-patterns) | Interview patterns in Java organised by how to recognise the problem: two pointers, sliding window, monotonic stack, binary search on the answer, heaps, graphs, DP, tries and more. | 52 tests, each solution checked against a brute force on thousands of random inputs |

#### AI agents and RAG

| Project | What it is | Evidence |
|---|---|---|
| [**agentic-bug-repair**](https://github.com/RakshitRPathak/agentic-bug-repair) | Agent that repairs failing Java repos: code graph + hybrid retrieval, fault localization, patch synthesis (mutation search, then any OpenAI-compatible model), sandboxed verification, GitHub webhook service and a review dashboard. JDK only. | 11 of 17 seeded bugs fixed and verified on a clean checkout. With a local qwen2.5-coder:7b on an RTX 5050 it also fixed a bug that needs new code, in 1 of 2 runs. The benchmark refuses to report a model result if the model failed. 158 tests |
| [**BankShield**](https://github.com/RakshitRPathak/bankshield) | RAG over a bank's policy documents *and* live (simulated) GCP state: hybrid retrieval, clearance filtering before scoring, a citation enforcer that withholds any answer not citing a retrieved clause, attack paths, hash-chained audit trail. FastAPI. | 98-question eval: recall 74/74, cited and faithful 75/75. With a local qwen2.5:7b: 67/67 shown answers cited and faithful, 8 uncited ones withheld by the enforcer, held-out refusals 21/22 vs 20/22. 115 tests |

#### Backend

| Project | What it is | Evidence |
|---|---|---|
| [**Healthcare Appointment & Follow-up Manager**](https://github.com/RakshitRPathak/Healthcare-Appointment-Follow-up-Manager) | Node + TypeScript + PostgreSQL. Double-booking is impossible by construction (row locks plus `EXCLUDE` constraints), emails go through a transactional outbox with retries and a dead-letter queue, and LLM visit summaries are schema-validated with a deterministic fallback. | 51 integration tests against real Postgres, including concurrency races |
| [**PDF-to-Audio**](https://github.com/RakshitRPathak/Pdf-Audio-converter) | Flask service that turns text PDFs into narration: text re-flow, chunked TTS with retry and backoff, background jobs with cancel and caching, swappable speech backends. | 34 offline tests |
| [**Inventory Management**](https://github.com/RakshitRPathak/Inventory-management-system) | Inventory REST API: RBAC, PBKDF2, signed tokens, hash-chained tamper-evident audit log, sensor telemetry reconciliation, optional RAG Q&A. | 15 tests, standard library only |

#### Research code (each repo reproduces every table and figure of its paper)

| Project | Problem | Result |
|---|---|---|
| [**VeriCloud**](https://github.com/RakshitRPathak/VeriCloud) | News claim verification that holds up against coordinated sybil campaigns | Under attack, macro-F1 0.79 vs 0.70 for the best baseline (8/8 seeds). Ties baselines on clean data |
| [**RailConflict-PSCL**](https://github.com/RakshitRPathak/RailConflict-PSCL) | Railway collision-risk classification with a physics shield and conformal escalation | Missed-Critical encounters cut from 9.9% to 0.7% (10 seeds × 24,000 encounters) |
| [**TrustDecay-TKG**](https://github.com/RakshitRPathak/TrustDecay-TKG) | Choosing which IT assets to audit, using temporal knowledge graphs | 54% precision at a 10% audit budget vs 16% for rotation audits |
| [**OpinionLineage-OLS**](https://github.com/RakshitRPathak/OpinionLineage-OLS) | Organic sentiment from streams full of reposts, bots and AI rewrites | Provenance error cut 2.5×; exact retroactive correction in 0.04 s vs 528 s for a full reprocess |

The research results come from simulation studies or public benchmark data, as each README states. They are not field deployments.

<details>
<summary><b>More projects</b></summary>

* [Wildfire risk prediction](https://github.com/RakshitRPathak/Wildfire-prediction-ml-model): scikit-learn ensemble and Flask dashboard on the UCI Forest Fires data, reporting measured accuracy next to the projected figures. Models are monotone in the fire-weather features, with tests that enforce it.
* [Mine tremor detection](https://github.com/RakshitRPathak/Mining-tremor-detection-Patent-cum-grant): edge-AI simulation with Random Forest, physical-threshold validation and multi-node consensus.
* [Risk-constrained emergency control](https://github.com/RakshitRPathak/Risk-Constrained-Emergency-Control-System): classifier that screens micro-interventions for safety before physical testing, with tests that pin the safety thresholds.

</details>

---

#### Experience

* **Software Engineering Intern, aiDataWorks** (May–Jul 2026): RAG and LLM features for a healthcare product on Google Cloud; data-governance and security policies for three client engagements.
* **Computer Science Intern, THDC India Ltd.** (May–Jun 2025): SCADA/PLC, SQL/ERP, networking and cybersecurity at the Khurja Super Thermal Power Project.

#### Tools

**Languages:** C++, Java, Python, TypeScript, SQL, CUDA &nbsp;·&nbsp; **Backend:** Node, Express, Flask, PostgreSQL, Redis, BullMQ &nbsp;·&nbsp; **ML:** scikit-learn, PyTorch, TensorFlow, RAG, OpenAI API, Ollama &nbsp;·&nbsp; **Other:** Docker, CMake, Git, Google Cloud, Power BI

Secretary, IEEE Power & Energy Society student chapter (VIT) &nbsp;·&nbsp; Black belt and assistant instructor, karate
