<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

`thc1006` — GitHub display name 秀吉 (Hideyoshi)

**Nephio (LF Networking) Technical Steering Committee Member** — cloud-native telecom and AI-RAN researcher, and a medical clerk.

From RTOS on microcontrollers and satellite antennas, through cloud-native 5G / O-RAN automation, up to AI for networks and medicine — I work the whole path from silicon to cloud to bedside.

[Website](https://people.cs.nycu.edu.tw/~hctsai1006/) &nbsp;·&nbsp; [Open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/) &nbsp;·&nbsp; [CNCF DevStats: 1,712](https://devstats.cluster.fun/?user=thc1006) &nbsp;·&nbsp; [ORCID](https://orcid.org/0000-0001-7421-8027) &nbsp;·&nbsp; [LinkedIn](https://linkedin.com/in/thc1006)

</div>

---

## Cloud native, in numbers

| | |
|---|---|
| **CNCF DevStats score** | **[1,712](https://devstats.cluster.fun/?user=thc1006)** (121 PRs · 57 issues) |
| **Merged upstream PRs** | **97** across **46** independent projects |
| **Within CNCF** | **80 merged PRs across 41 CNCF repositories** |
| **Governance** | Nephio **TSC Member** (LF Networking) — [official roster](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667) · Zephyr **M5Stack Platforms Maintainer** (LF) |
| **LF credentials** | [Credly](https://www.credly.com/users/hsiu-chi-tsai) — Zephyr Technical Contributor · LFC102 Inclusive Open Source Community Orientation · LFS179 Introduction to Nephio |
| **Peer review** | JOSS (Journal of Open Source Software) — 3 reviews · IEEE WF-PST 2026 TPC |

Every merged PR is listed and linked here: **[people.cs.nycu.edu.tw/~hctsai1006/open-source](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

## What I actually do upstream

I look for **bug classes**, not patch counts.

**A worked example — int64 overflow in Dynamic Resource Allocation quota accounting:**

1. Filed [`kueue#12896`](https://github.com/kubernetes-sigs/kueue/issues/12896) — DRA device counts could overflow int64, admitting over-quota Workloads and corrupting ClusterQueue accounting.
2. Fixed it myself across four PRs ([`#12897`](https://github.com/kubernetes-sigs/kueue/pull/12897), [`#12909`](https://github.com/kubernetes-sigs/kueue/pull/12909), [`#12945`](https://github.com/kubernetes-sigs/kueue/pull/12945), [`#12954`](https://github.com/kubernetes-sigs/kueue/pull/12954)) — saturating arithmetic, a `SafeValue` primitive, and the tests to pin the rounding semantics.
3. Recognized the same class in another scheduler and generalized it to **Volcano** ([`#5621`](https://github.com/volcano-sh/volcano/pull/5621) + backport [`#5626`](https://github.com/volcano-sh/volcano/pull/5626)), where it was a genuine quota bypass — building the project its first saturating primitives.
4. Escalated the underlying contract question to core: [`kubernetes/kubernetes#140424`](https://github.com/kubernetes/kubernetes/issues/140424) — *define an upper bound or overflow-safety contract for device request count* (sig/scheduling · sig/node · sig/api-machinery · wg/device-management).

**Selected CNCF projects I have merged into:** Kubernetes · Kueue · Volcano · OpenTelemetry (`opentelemetry-cpp` ×20, Collector, Android, Helm charts) · Jaeger UI · Milvus · Envoy · Helm · KEDA · Harbor · Keycloak · minikube · kubespray · Meshery · Perses · Cortex · OpenTofu · KubeStellar · dranet · dra-driver-cpu · llm-d · OperatorHub · kpt/porch · Nephio.

**Beyond CNCF:** Zephyr RTOS (4-core SMP bring-up on a GIC-less BCM2710, carried upstream by the maintainer) · ASWF · PyTorch Foundation · Docker · Hugging Face · SGP4 satellite orbit propagation · RocketPy.

## Community

- **Community organizer** — "O-RAN in B5G/6G" community track, **COSCUP** (Taiwan's largest open source conference), after two years as a speaker there.
- **Speaker** — COSCUP 2022 / 2023 / 2025 · SITCON × Academia Sinica · GDG Kaohsiung · Google I/O Extended 2023 & 2024.
- **Founder** — Google Developer Student Club at NYCU (~200 members); GDSC Lead at Czech Technical University, Prague. Ran Taiwan's first **Google I/O Extended Hsinchu** (2023).
- **In Taiwanese and Hakka** — I give technical talks in Taiwanese (Tâi-gí), including a 5G / O-RAN lecture at Academia Sinica, and led "語您童行", a team doing science communication in Taiwanese and Hakka.
- **Teaching** — cloud-native and O-RAN tutorials, lecture videos, and course materials in Traditional Chinese; first Traditional Chinese article ever published on Google Dev Library.

## Selected honors

| Year | Honor |
|------|-------|
| 2023 | **Presidential Education Award** (總統教育獎, Diligence Category) — Taiwan's highest student honor |
| 2026 | **NSTC College Student Research Creativity Award** — "LLM- and Nephio-driven automation of cloud-native O-RAN network functions" (adviser: Prof. Chien-Chao Tseng, NYCU CS WinLab) |
| 2026 | **Taiwan Space Agency (TASA) Young Space Professionals Program**, 5th cohort — selected among 40 nationwide |
| 2026 | **Make NTU · PANJIT Enterprise Award — 1st Place** — TinyML voice-controlled dexterous hand |
| 2025 | **IEEE Region 10 ACEI Program** |
| 2025 | **MeiZhu Hackathon — 1st Place** |
| —    | **Microsoft Youth Hero Award**, Taiwan — one of five nationwide |

<details>
<summary><b>Research and publications</b></summary>

<br>

**ORCID:** [0000-0001-7421-8027](https://orcid.org/0000-0001-7421-8027) — 10 papers and preprints, 2023–2026.

- *Ground-Side Mission Plan Compilation with Policy-as-Code Guardrails for Cloud-Native Satellite Platforms* — **IEEE SCC 2026, accepted**.
- *Physics-Grounded Deep Reinforcement Learning for Power Control in LEO Non-Terrestrial O-RAN* — an honest benchmark: a converged PPO policy does not beat a well-tuned classical controller anywhere in the operating envelope. Contributes a causal SGP4 + 3GPP TR-38.811 environment and an E2SM-NTN service model.
- *Cross-Layer Diagnostics for Operator-Side Platform Porting of GPU-Accelerated 5G RAN* — NVIDIA Aerial cuBB on DGX Spark.
- *Federated O-RAN Slice SLA Prediction* — cross-architecture benchmark on Colosseum / ColO-RAN.

Full list: **[people.cs.nycu.edu.tw/~hctsai1006/publications](https://people.cs.nycu.edu.tw/~hctsai1006/publications/)**

</details>

## Currently

- **Research Assistant** — NYCU WinLab / Office of AI Affairs (adviser: Prof. Chien-Chao Tseng).
- **Antenna-in-Package (AiP) for satellite NTN** — summer research residency under Taiwan's MOEA space-and-network industry program.
- **Clerk (Neurology and Cardiology)** — Taipei City Hospital, Yangming Branch.

## Education

Interdisciplinary by design — National Yang Ming Chiao Tung University (AI and biomedicine), Charles University Faculty of Medicine (Czechia), and Czech Technical University 6Gmobile Lab, with exchange study at POSTECH, SJTU, and Hanyang.

## Tech

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnubash&logoColor=white)
&nbsp;
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Zephyr](https://img.shields.io/badge/Zephyr%20RTOS-8A2BE2?style=flat&logo=zephyrproject&logoColor=white)

## Connect

- Website — <https://people.cs.nycu.edu.tw/~hctsai1006/> · <https://thc1006.us>
- Email — hctsai@linux.com · thc1006@ieee.org
- LinkedIn — <https://linkedin.com/in/thc1006> · X — [@thc1006](https://x.com/thc1006)
- LFX — <https://openprofile.dev/profile/thc1006>

---

<div align="center">

<sub>From a fishing village in Dapeng Bay, Pingtung. I give technical talks in Taiwanese, and I hold that research owes something back to the people who made it possible.</sub>

<br><br>

<img src="https://github-readme-stats.vercel.app/api?username=thc1006&show_icons=true&count_private=true&hide_title=true&hide_border=true&theme=graywhite" alt="thc1006 on GitHub" height="150" />

</div>
