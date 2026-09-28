<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/vagabond_dark.jpg">
  <source media="(prefers-color-scheme: light)" srcset="assets/vagabond_banner.jpg">
  <img src="assets/vagabond_dark.jpg" alt="Sharvin Neve // 浪人・宮本武蔵 // Systems Software & AI Infrastructure" width="100%">
</picture>

# SHARVIN NEVE
### 彷徨の道 // Systems Software & AI Infrastructure Engineer
**`RTEMS Space Kernel Contributor` · `Distributed LLM Inference` · `Delta-RoPE / AgentKV` · `Edge Fleet Telemetry`**

[**GitHub**](https://github.com/Guts1005) &nbsp;•&nbsp; [**LinkedIn**](https://linkedin.com/in/sharvinneve) &nbsp;•&nbsp; [**Email**](mailto:sharvinneve67@gmail.com) &nbsp;•&nbsp; [**Download CV (PDF)**](Sharvin_Neve_CV.pdf)

</div>

---

> *"Preoccupied with a single leaf, you will not see the tree. Preoccupied with a single tree, you will miss the entire forest."*  
> *"Do not seek to follow in the footsteps of the wise; seek what they sought."*  
> — **Miyamoto Musashi, *The Book of Five Rings* / Takehiko Inoue's *Vagabond***

Rather than remaining at the superficial layer of high-level API abstractions and cookie-cutter frameworks, I engineer downward into the bedrock: operating system kernel timers, GPU memory hierarchies, KV cache geometry, and low-latency edge daemons under strict physical constraints.

---

### // 零一・奥義 ── Flagship Research & Architectures

#### 1. **[AgentKV](https://github.com/Guts1005/segkv-showcase)** — Arbitrary-Position KV Cache Reuse for Multi-Agent LLMs via Delta-RoPE
*Mathematical elimination of redundant prefill compute in collaborative multi-agent swarms.*

- **The Multi-Agent Flaw**: State-of-the-art inference engines (vLLM, SGLang) rely on Radix Tree Automatic Prefix Caching (APC), which requires exact prompt alignment from token position 0. In multi-agent swarms sharing large tool specifications, differing agent prefixes trigger an immediate 0% cache hit, forcing full multi-second prefills.
- **Delta-RoPE Invariant**: Exploits the group-additive properties of Rotary Positional Embeddings: Key vectors obey 2D orthogonal rotation, while Value vectors are position-invariant. Shifting a cached KV block across sequence positions requires only **4 FLOPs per coordinate pair** via a single 2D Givens rotation.
- **RTX 3060 12GB Benchmark Proof** (Qwen 2.5 7B, 1,500 shared tokens):
  - **Compute Cost**: Slashed from **22.118 TFLOPs** to **147.456 MFLOPs** (**149,995x fewer FLOPs**).
  - **Rotation Kernel Execution**: **0.28 ms** vs ~1,105.9 ms (**3,949x faster**).
  - **Analytical Precision**: **7.257e-13** max Float64 error (bit-for-bit exact at machine precision, 0.999931 attention cosine similarity).
  - **Multi-Agent Pipeline**: **3.23x overall pipeline speedup** (7.08x TTFT speedup) across a 5-agent collaborative workflow.

🔗 **[Explore Repository & Math Proof](https://github.com/Guts1005/segkv-showcase)** · `python verify_rope.py`

---

#### 2. **High-Throughput LLM Serving & Continuous Dynamic Batching**
*Empirical throughput scaling and memory-bounded serving harness for open-weights LLMs.*

- **10.35x Throughput Scaling**: Scaled Qwen 2.5 7B from 57.2 tok/s to **592.0 tok/s** across 20 concurrent request streams on an Ampere 12GB GPU.
- **PagedAttention & Marlin GEMM**: Deployed AutoAWQ Marlin W4A16 GEMM kernels to reserve 3.6 GiB VRAM for a **67,440-token PagedAttention KV-cache pool**.
- **Latency Bounding**: Sustained an **87.1% Radix-Tree Prefix Cache hit rate**, reducing P50 Time-To-First-Token (TTFT) to **38.7 ms**.

---

#### 3. **[Streaming-Rpi](https://github.com/Guts1005/Streaming-Rpi)** — Production Wearable Edge Video & Telemetry Stack
*Industrial edge streaming, sensor acquisition, and AI safety platform on ARM/Raspberry Pi.*

- **Sub-300ms Glass-to-Glass Latency**: Hardware-accelerated H.264 video ingestion feeding an embedded Simple Realtime Server (SRS) Docker container, delivered via HTTP-FLV (`mpegts.js`) with two-way WebRTC audio talkback to a Next.js 16 / React 19 control plane.
- **Offline-First & Auto-Chunking**: GPIO button triggers 5-minute segmented recording (`ffmpeg`) with automated sequential cloud synchronization and headless camera-based QR Wi-Fi provisioning.
- **Zero-Trust Network Perimeter**: Outbound Cloudflare Tunnels (`cloudflared`) bypassing carrier-grade NAT across 4 industrial field sites with zero open inbound firewall ports.

🔗 **[Explore Streaming-Rpi Repo](https://github.com/Guts1005/Streaming-Rpi)** · **[v1.0.0 Release](https://github.com/Guts1005/Streaming-Rpi/releases/tag/v1.0.0)**

---

#### 4. **[ChurnIQ](https://github.com/Guts1005/ChurnIQ)** — Predictive ML Pipeline & Telemetry Platform
- End-to-end predictive pipeline with 10 cross-validated models and a Voting Classifier ensemble achieving **84.93% ROC-AUC**.
- High-concurrency FastAPI backend with interactive React & Streamlit feature importance visualizers.

---

### // 零二・鍛錬 ── Upstream Core & Kernel Contributions

Patches to space-grade operating systems, foundation inference runtimes, and Linux primitives:

| Repository / Project | Target File / PR | Architectural Scope & Impact |
| :--- | :--- | :--- |
| **[RTEMS Kernel](https://gitlab.rtems.org/rtems/rtos/rtems)** | `coretodcheck.c` & `clock.h` | **Space-Grade RTOS**: Hardened watchdog timer validation logic and POSIX clock boundary checks across kernel core routines for NASA & ESA mission profiles; resolved 34-bit timer rollover constraints up to year 2400. |
| **[sgl-project/sglang](https://github.com/sgl-project/sglang)** | [`PR #38228`](https://github.com/sgl-project/sglang/pull/38228) | **Distributed LLM Inference**: Implemented Prometheus `avg_request_queue_latency` telemetry across distributed streaming queues for high-throughput inference monitoring. |
| **[vllm-project/flash-attention](https://github.com/vllm-project/flash-attention)** | [`PR #194`](https://github.com/vllm-project/flash-attention/pull/194) | **GPU Acceleration**: Hoisted preprocessor directives from macro expansions for MSVC compiler conformance on NVIDIA Hopper GPU architectures. |
| **[harsh-nod/fe2o3](https://github.com/harsh-nod/fe2o3)** | [`PR #273`](https://github.com/harsh-nod/fe2o3/pull/273) | **Linux Systems**: Hardened Linux `memfd_create` file sealing against bounded `EBUSY` collision windows under heavy concurrent process forks. |
| **[Guts1005/gmail-oauth-mailer](https://github.com/Guts1005/gmail-oauth-mailer)** | [Repository](https://github.com/Guts1005/gmail-oauth-mailer) | **Developer Tooling**: Diagnosed and resolved async socket timeout race conditions in automated headless CI test harness; designed for modular npm packaging. |

---

### // 零三・実戦 ── Production Systems & Industrial Deployments

#### **Embedded Systems & Edge Platform Intern** — *Aspire Consultancy Services*
*(May 2026 – July 2026)*
- **Distributed Edge Cluster**: Architected a headless telemetry and video ingestion pipeline across a 6-node ARM edge cluster at 4 industrial sites, processing **18GB of multimodal footage** and **14,750+ telemetry events**.
- **Low-Footprint C++ Daemon**: Engineered an edge supervisor daemon with a **<45MB RAM footprint**, circular memory ring buffers, and `systemd` watchdog supervision, eliminating crash-loops and recovering cleanly from network dropouts.
- **Low-Latency Streaming**: Built a sub-300ms WebRTC pipeline (LiveKit / SRS) with hardware H.264 encoding for automated remote aerial inspection, dual-track recording, and real-time visual telemetry capture.

#### **Embedded Firmware & Sensor Interfacing Intern** — *Entice Engineering*
*(Aug 2025 – Dec 2025)*
- **Sub-5ms Sensor Acquisition**: Interfaced camera and GPIO/UART/SPI sensors on ARM Cortex boards, hitting sub-5ms acquisition latency.
- **Firmware Data Pipelines**: Optimized high-throughput circular buffer event serialization in C and Python deployed directly on active field hardware.

---

### // 零四・目録 ── Technical Arsenal

| Domain | Systems, Frameworks & Hardware |
| :--- | :--- |
| **Languages & Systems** | `Modern C++ (C++17/20)` · `C (C99/C11)` · `Python 3.12` · `CUDA` · `Bash` · `SQL` · `Rust (Foundations)` |
| **AI Systems & LLM Infra** | `vLLM` · `SGLang` · `PagedAttention` · `FlashAttention` · `AutoAWQ Marlin` · `PyTorch` · `Prefix Caching (APC)` |
| **Kernel, Embedded & Edge** | `RTEMS Space RTOS` · `Linux Kernel (systemd/POSIX)` · `ARM Cortex / Raspberry Pi` · `V4L2` · `FFmpeg` · `GPIO / UART / SPI` |
| **Media, Networking & Cloud** | `WebRTC (LiveKit / SRS)` · `FastAPI` · `Next.js` · `Docker (arm64/amd64)` · `Cloudflare Tunnels` · `Prometheus` · `AWS` |
| **Profiling & Diagnostics** | `GDB` · `Valgrind` · `Linux Perf / Tracing` · `CMake` · `GitHub Actions` · `CodeQL` · `Gitleaks` |

---

### // 零五・研鑽 ── Active Research & Inquiries

- **Arbitrary-Position KV Cache Scheduling**: Generalizing Delta-RoPE Givens transformations across multi-head and grouped-query attention in distributed inference clusters.
- **Space-Grade Kernel Verification**: Formal timing boundaries and deterministic lock-free ring buffers on RTEMS for extreme radiation and deep-space missions.
- **Zero-Copy Edge Telemetry**: Writing eBPF socket filters for zero-overhead packet telemetry on constrained ARM devices.

---

### // 零六・印章 ── Verified Credentials & Recognition

- 🥇 **Smart India Hackathon (SIH)** — *National Finalist (Hardware & Autonomous Systems Track)*
- ☁️ **AWS Academy Graduate** — *Cloud Architecting (AWS Training Badge, 2026)*
- ☁️ **AWS Cloud Quest** — *Cloud Practitioner Verified Badge*
- 📜 **NPTEL Elite Certificate** — *Design Practices for Intelligent Product Design (IIT Kanpur)*
- 🎓 **NMIMS MPSTME, Mumbai** — *Integrated B.Tech + MBA Tech in Computer Engineering (2023 – 2028, CGPA: 3.4/4.0)*

---

### // 零七・歩み ── Engineering Cadence & Commit Velocity

<div align="center">

<a href="https://github.com/Guts1005">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com/?user=Guts1005&theme=dark&background=0d1117&border=30363d&stroke=30363d&ring=b91c1c&fire=b91c1c&currStreakNum=ffffff&sideNums=ffffff&currStreakLabel=b91c1c&dates=94a3b8">
    <source media="(prefers-color-scheme: light)" srcset="https://streak-stats.demolab.com/?user=Guts1005&theme=light&background=ffffff&border=e2e8f0&stroke=e2e8f0&ring=b91c1c&fire=b91c1c&currStreakNum=0f172a&sideNums=0f172a&currStreakLabel=b91c1c&dates=64748b">
    <img src="https://streak-stats.demolab.com/?user=Guts1005&theme=dark&background=0d1117&border=30363d&stroke=30363d&ring=b91c1c&fire=b91c1c&currStreakNum=ffffff&sideNums=ffffff&currStreakLabel=b91c1c&dates=94a3b8" alt="Sharvin's GitHub Streak" width="70%">
  </picture>
</a>

</div>

---

<div align="center">

> *"All that you are is the result of what you have thought. The sword must become one with the soul."*  
> — **Miyamoto Musashi**

Whether you are building high-throughput distributed inference engines, space-grade kernel systems, or constrained edge fleets — my door is open.

[**Connect on LinkedIn**](https://linkedin.com/in/sharvinneve) &nbsp;•&nbsp; [**Send an Email**](mailto:sharvinneve67@gmail.com) &nbsp;•&nbsp; [**Follow on GitHub**](https://github.com/Guts1005)

</div>
