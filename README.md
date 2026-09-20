<div align="center">

# ?Sharvin <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExemNwbW5hdzB4OGNtcTNuMXA5cTNxNGdxNHlrcGwzN2pneTFidjh3cCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/qiD272jWSEPSQ5lEWL/giphy.gif" width="28">

**Systems Software & AI Infrastructure · Distributed LLM Inference · Edge Fleet Telemetry**

Integrated B.Tech + MBA (Computer Engineering) @ **NMIMS MPSTME, Mumbai** · *Class of 2028*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sharvinneve)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Guts1005)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sharvinneve67@gmail.com)

</div>

---

```bash
sharvin@edge-node:~$ neofetch --profile
OS: Linux / Edge Fleet Architecture (6-node distributed cluster)
Host: NMIMS MPSTME, Mumbai (Integrated B.Tech + MBA Tech '28)
Kernel: Modern C++20, Python, POSIX pthreads, WebRTC
Experience: Software & Systems Intern @ Aspire Consultancy Services | Ex-Intern @ Entice Engineering
Core Focus: Distributed LLM Inference (vLLM, SGLang) & High-Throughput Edge Telemetry
Current State: Architecting offline-first streaming daemons & instrumenting AI infrastructure
```

---

## ❕ Executive Summary

I am a computer engineering student and systems software engineer building at the intersection of **low-level systems** and **applied AI infrastructure**. 

Rather than stopping at high-level API wrappers, I work deep in the stack: contributing latency telemetry upstream to tier-1 LLM inference engines (**SGLang**, **vLLM / FlashAttention**), engineering memory-constrained C++ daemons for multi-node edge camera fleets, and shipping full-stack predictive ML platforms. My guiding ethos: *if it doesn't survive network partitions and high I/O concurrency, it isn't ready for production.*

---

## 😌 Upstream Systems & Open Source Contributions

A selection of upstream pull requests contributed to production AI inference engines and systems infrastructure:

| Repository | Pull Request / Patch | Architectural Scope & Impact |
| :--- | :--- | :--- |
| **[sgl-project/sglang](https://github.com/sgl-project/sglang)** | [`PR #38228`](https://github.com/sgl-project/sglang/pull/38228) | **Distributed LLM Inference**: Instrumented Prometheus latency telemetry across distributed streaming queues for high-throughput inference monitoring. |
| **[vllm-project/flash-attention](https://github.com/vllm-project/flash-attention)** | [`PR #194`](https://github.com/vllm-project/flash-attention/pull/194) | **GPU Acceleration**: Hoisted preprocessor directives from macro expansions for MSVC compiler conformance on NVIDIA Hopper architectures. |
| **[harsh-nod/fe2o3](https://github.com/harsh-nod/fe2o3)** | [`PR #273`](https://github.com/harsh-nod/fe2o3/pull/273) | **Linux Systems**: Hardened Linux `memfd_create` file sealing against bounded `EBUSY` collision windows under heavy concurrent process forks. |
| **[Guts1005/gmail-oauth-mailer](https://github.com/Guts1005/gmail-oauth-mailer)** | [Repository](https://github.com/Guts1005/gmail-oauth-mailer) | **Developer Tooling**: Diagnosed and resolved async socket timeout race conditions in automated CI test harnesses; designed for modular npm packaging. |

---

## ⚒ Production Systems & Work Experience

### **Software & Systems Engineering Intern** — *Aspire Consultancy Services*
*(May 2026 – July 2026)*
- **Distributed Edge Telemetry**: Architected an offline-first distributed telemetry and video data pipeline across a 6-node edge fleet, reliably ingesting **18GB of multimodal footage** and **14,750+ telemetry events** across intermittent network partitions.
- **Low-Footprint C++ Daemon**: Engineered an edge supervisor daemon in C++ with a **<45MB RAM footprint** and `systemd` watchdog supervision, achieving zero crash-loops and continuous automated cloud re-synchronization.
- **Sub-300ms Live Streaming**: Integrated WebRTC streaming (LiveKit + FFmpeg + Next.js) and multimodal API ingestion for automated real-time inspection, dual-track recording (local & desktop), and AI snapshot comparison.

### **Systems Software Intern** — *Entice Engineering*
*(Aug 2025 – Dec 2025)*
- **High-Throughput Serialization**: Built event serialization routines in C and Python, hitting **sub-5ms data acquisition latency** under sustained high-I/O sensor throughput.
- **Hardware Integration**: Developed automated hardware integration and telemetry synchronization pipelines deployed across production sensor systems.

---

## 🙈 Flagship Projects

### **1. ChurnIQ — Predictive Analytics & ML Pipeline Platform**
*Production-grade machine learning platform for customer churn analytics with automated feature transformation and real-time scoring.*

- **Calibrated Ensemble Model**: Engineered an end-to-end predictive pipeline analyzing high-dimensional user interaction data, achieving an **84.93% ROC-AUC** with calibrated XGBoost and LightGBM models.
- **Full-Stack Architecture**: Built a high-concurrency FastAPI backend with interactive React & Streamlit evaluation dashboards for lead triage and feature importance visualizers.

![XGBoost](https://img.shields.io/badge/XGBoost-151515?style=flat-square)
![LightGBM](https://img.shields.io/badge/LightGBM-184E77?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)

---

### **2. Smart Helmet Live (`Streaming-Rpi`) — Industrial Edge Video & AI Safety System**
*Industrial-grade edge streaming, BLE beacon worker tracking, and Google Gemini AI safety platform for Raspberry Pi.*

- **Sub-300ms Low-Latency Streaming**: Hardware-encoded H.264 video ingested into Simple Realtime Server (SRS) and delivered via HTTP-FLV (`mpegts.js`) with two-way WebRTC audio talkback to the Next.js control center.
- **Offline-First & Auto-Chunking**: GPIO button triggers 5-minute segmented recording (`ffmpeg`) with automated sequential cloud synchronization and headless camera-based QR Wi-Fi provisioning.
- **Zero-Trust Security & SQA**: Enforces zero open inbound ports via Cloudflare Tunnels, strict Content-Security-Policy (CSP), tenant device isolation, and automated **GitHub CodeQL AST** and **Gitleaks** quality gates.

[![CI](https://github.com/Guts1005/Streaming-Rpi/actions/workflows/ci.yml/badge.svg)](https://github.com/Guts1005/Streaming-Rpi/actions/workflows/ci.yml)
[![CodeQL](https://github.com/Guts1005/Streaming-Rpi/actions/workflows/codeql.yml/badge.svg)](https://github.com/Guts1005/Streaming-Rpi/actions/workflows/codeql.yml)
[![Raspberry Pi](https://img.shields.io/badge/Raspberry_Pi-A22846?style=flat-square&logo=raspberrypi&logoColor=white)](https://raspberrypi.org)
[![SRS](https://img.shields.io/badge/Streaming-SRS%205-red?style=flat-square&logo=docker&logoColor=white)](https://github.com/ossrs/srs)
[![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)](https://nextjs.org/)
[![Gemini AI](https://img.shields.io/badge/Google%20Gemini-8E75C2?style=flat-square&logo=google&logoColor=white)](https://ai.google.dev/)

[→ Streaming-Rpi Flagship Repo](https://github.com/Guts1005/Streaming-Rpi) · [→ Official v1.0.0 Release](https://github.com/Guts1005/Streaming-Rpi/releases/tag/v1.0.0) · [→ Centrix-Helmet Repo](https://github.com/Guts1005/Centrix-Helmet)

---

<details>
<summary><strong>📂 View Additional Engineering Projects</strong></summary>

<br>

#### **ShiftLeft Testing Dashboard**
*AI-augmented developer tooling & automated defect prediction.*
- Integrates Google Gemini API to analyze automated continuous integration test runs, predict recurring defect hotspots, and generate actionable telemetry for engineering teams.
- **Stack:** Python, Google Gemini API, React, Node.js.

#### **Gmail OAuth Mailer**
*Reusable, production-hardened OAuth 2.0 mail dispatch engine.*
- Abstracted complex Google OAuth 2.0 authentication flows into an npm-ready library. Hardened against asynchronous socket timeout race conditions under high-throughput queues.
- **Stack:** Node.js, OAuth 2.0, Mocha/Chai.

</details>

---

## 🛠️ Technical Arsenal

<div align="center">

| Domain | Technologies & Frameworks |
| :--- | :--- |
| **Systems & Languages** | `C++17/20` · `C (C99/C11)` · `Python` · `TypeScript` · `JavaScript` · `SQL` · `Bash` · `Rust (Foundations)` |
| **AI Systems & LLM Infra** | `SGLang` · `vLLM` · `FlashAttention` · `PyTorch` · `Scikit-learn` · `LangChain` · `LlamaIndex` · `Prometheus` |
| **Backend & Distributed** | `FastAPI` · `Next.js` · `Node.js` · `React` · `WebRTC / LiveKit` · `WebSockets` · `Docker` · `Redis` · `PostgreSQL` |
| **Edge, Cloud & Tools** | `Raspberry Pi` · `Linux Kernel (systemd/POSIX)` · `FFmpeg` · `AWS Cloud Practitioner` · `GitHub Actions` · `CMake` · `GDB` |

</div>

---

## 🔭 Research & What's on the Horizon

- **Distributed KV Cache & Memory Scheduling**: Exploring PagedAttention memory layouts and chunked prefill dynamics across distributed inference instances (vLLM / SGLang).
- **Agentic Workflows via Model Context Protocol (MCP)**: Building multi-agent systems with deterministic tool routing, dynamic context pruning, and sandboxed execution boundaries.
- **Kernel-Level Observability**: Writing eBPF probes for zero-overhead telemetry tracking on edge Linux daemons and low-latency network sockets.

---

## 🏆 Accolades & Certifications

- 🥇 **Smart India Hackathon (SIH)** — *National Finalist (Hardware & Systems Software Track)*
- ☁️ **AWS Cloud Quest: Cloud Practitioner** — *Verified Cloud Architecture Credential*
- 📜 **NPTEL Elite Certificate** — *Design Practices for Intelligent Product Design (IIT Kanpur)*
- 🎸 **Musician & Band Member** — *Practicing creative discipline, live rhythm, and team dynamics*

---

## 📊 GitHub Footprint & Analytics

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Guts1005&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58a6ff&icon_color=58a6ff&text_color=c9d1d9" alt="Sharvin's GitHub Stats" width="48.5%">
  <img src="https://streak-stats.demolab.com/?user=Guts1005&theme=tokyonight&hide_border=true&background=0d1117&ring=58a6ff&fire=58a6ff&currStreakLabel=58a6ff" alt="Sharvin's GitHub Streak" width="48.5%">
</div>

<br>

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Guts1005&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9" alt="Top Languages" width="60%">
</div>

---

<div align="center">

### Let's Build Something High-Impact.

Whether you're working on distributed AI inference, edge systems, or ambitious engineering challenges — my inbox is always open.

[![LinkedIn](https://img.shields.io/badge/Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/sharvinneve)
[![Email](https://img.shields.io/badge/Send_an_Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sharvinneve67@gmail.com)
[![GitHub](https://img.shields.io/badge/Follow_on_GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Guts1005)

</div>
