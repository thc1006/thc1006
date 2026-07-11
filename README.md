<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

Open-source contributor working on Kubernetes resource management, observability, and cloud-native telecom.

I serve on the **Nephio Technical Steering Committee** under LF Networking, and work as a research assistant at National Yang Ming Chiao Tung University in Taiwan.

[Website](https://people.cs.nycu.edu.tw/~hctsai1006/) &nbsp;·&nbsp;
[Open-source work](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/) &nbsp;·&nbsp;
[CNCF DevStats](https://devstats.cluster.fun/?user=thc1006) &nbsp;·&nbsp;
[ORCID](https://orcid.org/0000-0001-7421-8027) &nbsp;·&nbsp;
[LinkedIn](https://linkedin.com/in/thc1006)

</div>

---

## Current focus

- Kubernetes scheduling, quota accounting, and Dynamic Resource Allocation
- Observability — OpenTelemetry SDKs and Jaeger UI
- Nephio, O-RAN, and cloud-native telecom automation
- Contributor onboarding and technical education, in English and Traditional Chinese

## Open-source work

*Snapshot: 12 July 2026. Every figure below is recomputed from the linked portfolio, not maintained by hand.*

| | |
|---|---|
| **CNCF DevStats** | **[1,712](https://devstats.cluster.fun/?user=thc1006)** |
| **Merged upstream** | **97 pull requests across 46 projects**, in 5 Linux Foundation sub-foundations |
| **Within CNCF** | **79 merged pull requests across 40 CNCF-hosted and Kubernetes-ecosystem repositories** |
| **Governance** | Nephio **Technical Steering Committee member**, LF Networking — [official roster](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667) |
| **Maintenance** | Zephyr **M5Stack platforms maintainer** |
| **Peer review** | Journal of Open Source Software — 3 reviews · IEEE WF-PST 2026 program committee |

A complete, linked list of every merged contribution is in my
**[open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**.

### Representative work: overflow-safe DRA quota accounting

I am particularly interested in recurring correctness problems that cross project boundaries. One recent series began with an `int64` overflow in Dynamic Resource Allocation quota accounting:

1. **Reported it.** [`kubernetes-sigs/kueue#12896`](https://github.com/kubernetes-sigs/kueue/issues/12896) — a sufficiently large device count could wrap the arithmetic, admit an impossible oversized Workload, and leave ClusterQueue accounting inconsistent.

2. **Fixed it.** Four merged pull requests in Kueue — [`#12897`](https://github.com/kubernetes-sigs/kueue/pull/12897), [`#12909`](https://github.com/kubernetes-sigs/kueue/pull/12909), [`#12945`](https://github.com/kubernetes-sigs/kueue/pull/12945), [`#12954`](https://github.com/kubernetes-sigs/kueue/pull/12954) — introducing saturating arithmetic, reusable safe-conversion helpers, and regression tests that pin the rounding semantics.

3. **Checked whether the same arithmetic class existed elsewhere.** It did. In Volcano the overflow could cause a quota check to accept an oversized request that should have been rejected; the fix and its release-branch backport were merged in [`volcano-sh/volcano#5621`](https://github.com/volcano-sh/volcano/pull/5621) and [`#5626`](https://github.com/volcano-sh/volcano/pull/5626).

4. **Raised the underlying contract question upstream.** [`kubernetes/kubernetes#140424`](https://github.com/kubernetes/kubernetes/issues/140424) — should device request counts carry an explicit upper bound, or should downstream consumers be required to use overflow-safe arithmetic?

These were treated as correctness and robustness problems, not as demonstrated resource-theft vulnerabilities. The linked issues and pull requests carry the reproductions, tests, review discussion, and the exact impact boundaries.

### Where I have contributed

- **CNCF-hosted and Kubernetes ecosystem** — Kubernetes, Kueue, Volcano, OpenTelemetry (C++, Collector, Android, Helm charts), Jaeger UI, Envoy, Helm, KEDA, Harbor, Keycloak, minikube, kubespray, Meshery, Perses, Cortex, OpenTofu, KubeStellar, kube-vip, kgateway, Microcks, llm-d, OperatorHub, kpt/Porch, dranet, dra-driver-cpu.
- **Other Linux Foundation sub-foundations** — Nephio (LF Networking), Milvus (LF AI & Data), Ray (PyTorch Foundation), Academy Software Foundation, Zephyr (Linux Foundation).
- **Elsewhere** — Docker, Hugging Face, SGP4 satellite orbit propagation, RocketPy, and an O-RAN CU/DU implementation on GitLab.

Contributions span Go, C, C++, TypeScript, Python, and Rust, across product code, tests, CI, and documentation. I try to keep each change small enough to review, respond carefully to feedback, and leave behind enough tests or docs that the next maintainer does not have to reconstruct my reasoning.

## Community

- **Organizer** — the *O-RAN in B5G/6G* community track at COSCUP, Taiwan's largest open source conference, after two years there as a speaker.
- **Speaker** — COSCUP, SITCON at Academia Sinica, GDG Kaohsiung, Google I/O Extended.
- **Student communities** — founded the Google Developer Student Club at NYCU (roughly 200 members), then served as a GDSC lead at Czech Technical University in Prague. Organized the first Google I/O Extended in Hsinchu, Taiwan.
- **Local-language outreach** — I give technical talks in Taiwanese (Tâi-gí), including a 5G and O-RAN lecture at Academia Sinica, and led a team doing science communication in Taiwanese and Hakka.
- **Teaching** — cloud-native and O-RAN tutorials, lecture videos, and course materials in Traditional Chinese, including a Traditional Chinese article published through Google Dev Library.

What I want to do next is help more people cross the gap from *using* cloud native software to *contributing* to it:

- publish bilingual contribution walkthroughs based on real review threads, not toy examples;
- run practical newcomer sessions in Mandarin and Taiwanese, so that entering the community does not require English first;
- help contributors read review conventions and project governance, which is usually the real barrier, not the code;
- connect telecom engineers with the CNCF communities working on scheduling, networking, observability, and policy.

I completed **LFC102 (Inclusive Open Source Community Orientation)** in July 2026 because I intend to do this work, not only to describe it.

## Selected recognition

- **2023 Presidential Education Award**, presented by Taiwan's Ministry of Education
- **2026 NSTC College Student Research Creativity Award** — LLM- and Nephio-assisted automation of cloud-native O-RAN network functions
- **2026 Taiwan Space Agency Young Space Professionals Program**, fifth cohort
- **2026 Make NTU, PANJIT Enterprise Award, first place** — TinyML voice-controlled dexterous hand

A fuller record is on my **[website](https://people.cs.nycu.edu.tw/~hctsai1006/honors/)**.

## Research

Cloud-native telecom, O-RAN and non-terrestrial networks, AI infrastructure, and biomedical applications.

- *Ground-Side Mission Plan Compilation with Policy-as-Code Guardrails for Cloud-Native Satellite Platforms* — accepted at IEEE SCC 2026.
- *Physics-Grounded Deep Reinforcement Learning for Power Control in LEO Non-Terrestrial O-RAN* — an evaluation in which a converged PPO policy did not outperform a tuned classical controller anywhere in the operating envelope; contributes a causal SGP4 and 3GPP TR-38.811 environment and an E2SM-NTN service model.
- *Cross-Layer Diagnostics for Operator-Side Platform Porting of GPU-Accelerated 5G RAN.*
- *Federated O-RAN Slice SLA Prediction.*

Full list — **[ORCID](https://orcid.org/0000-0001-7421-8027)** · **[publications](https://people.cs.nycu.edu.tw/~hctsai1006/publications/)**

## Current roles

- **Nephio Technical Steering Committee member**, LF Networking
- **Research assistant**, NYCU WinLab and Office of AI Affairs
- **Satellite Antenna-in-Package research resident**, Taiwan industry–academia program
- **Medical student**, completing clinical clerkships at Taipei City Hospital

## Contact

- Website — <https://people.cs.nycu.edu.tw/~hctsai1006/> · <https://thc1006.us>
- Email — hctsai@linux.com · thc1006@ieee.org
- LinkedIn — <https://linkedin.com/in/thc1006> · X — [@thc1006](https://x.com/thc1006)
- LFX — <https://openprofile.dev/profile/thc1006> · Credly — <https://www.credly.com/users/hsiu-chi-tsai>

---

<div align="center">

<sub>
Raised in a fishing village in Dapeng Bay, Pingtung. I care about making technical communities easier to enter, especially for people who do not start with an established professional network or English-first resources.
</sub>

</div>
