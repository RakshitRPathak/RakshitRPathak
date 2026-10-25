### Hi, I'm Rakshit 👋

Final-year B.Tech (Computer Science & Business Systems) at **VIT Vellore**, graduating 2027. I build backend systems, ML pipelines with honest evaluation, and lately compilers and GPU kernels. **6 patent applications** (5 published), **3 papers submitted to IEEE Access**.

**Looking for:** a 6-month SDE internship, January to June 2027.

---

#### Systems

| Project | What it is | Evidence |
|---|---|---|
| [**minic**](https://github.com/RakshitRPathak/minic) | A compiler in C++17: hand-written lexer, recursive-descent parser, semantic analysis, constant folding and dead-code elimination, bytecode generation with backpatching, and a stack VM. | 43 tests, run optimized and unoptimized; clean under ASan and UBSan |
| [**cuda-gpu-bench**](https://github.com/RakshitRPathak/cuda-gpu-bench) | CUDA kernels (naive vs tiled matmul, three reduction strategies) with a benchmark harness, PTX instruction analysis and a CPU emulator that runs the real kernels. | 33 emulator checks, also under ASan and TSan. GPU timings not yet measured |

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

* [Wildfire risk prediction](https://github.com/RakshitRPathak/Wildfire-prediction-ml-model): scikit-learn ensemble and Flask dashboard on the UCI Forest Fires data, reporting measured accuracy next to the projected figures.
* [Mine tremor detection](https://github.com/RakshitRPathak/Mining-tremor-detection-Patent-cum-grant): edge-AI simulation with Random Forest, physical-threshold validation and multi-node consensus.
* [Risk-constrained emergency control](https://github.com/RakshitRPathak/Risk-Constrained-Emergency-Control-System): classifier that screens micro-interventions for safety before physical testing.

</details>

---

#### Experience

* **Software Engineering Intern, aiDataWorks** (May–Jul 2026): RAG and LLM features for a healthcare product on Google Cloud; data-governance and security policies for three client engagements.
* **Computer Science Intern, THDC India Ltd.** (May–Jun 2025): SCADA/PLC, SQL/ERP, networking and cybersecurity at the Khurja Super Thermal Power Project.

#### Tools

**Languages:** C++, Python, TypeScript, SQL, CUDA &nbsp;·&nbsp; **Backend:** Node, Express, Flask, PostgreSQL, Redis, BullMQ &nbsp;·&nbsp; **ML:** scikit-learn, PyTorch, TensorFlow, RAG, OpenAI API &nbsp;·&nbsp; **Other:** Docker, CMake, Git, Google Cloud, Power BI

Secretary, IEEE Power & Energy Society student chapter (VIT) &nbsp;·&nbsp; Black belt and assistant instructor, karate
