<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

**Upstream systems engineer · Kubernetes correctness · Observability · Cloud-native telecom**

I turn individual defects into reusable system invariants, search for their variants across projects, and carry the fixes through regression tests to upstream merge.

</div>

|  |  |
| --- | --- |
| **Merged upstream** | **240 pull requests across 68 projects.** 169 of them in 44 CNCF-hosted and Kubernetes-ecosystem repositories. |
| **CNCF-related contributions** | [**3,782**](https://devstats.cluster.fun/?user=thc1006) |
| **Kubernetes** | [**GitHub org member**](https://github.com/kubernetes/org/issues/6498) |
| **Governance** | [**Nephio TSC member**](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667), LF Networking |
| **OpenTelemetry** | [**GitHub org member**](https://github.com/open-telemetry/community/issues/3597) |
| **Maintainer** | [**M5Stack Platforms**](https://github.com/zephyrproject-rtos/zephyr/blob/main/MAINTAINERS.yml) in upstream Zephyr, `status: maintained` |

Every merged contribution, listed and linked: **[open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

<sub>The CNCF-related contribution count refreshes automatically via GitHub Actions from CNCF DevStats' <code>GithubIDContributions</code> API — a contribution count, not a weighted score. Other figures are authored, merged, public upstream pull requests, reconciled August 2026.</sub>

### How I work — three engineering campaigns

Each starts from one defect and generalizes into a review invariant, then searches for that invariant's variants across projects.

**Resource accounting & Kubernetes DRA.** Schedulers and device-allocation paths audited against arithmetic and state invariants: sums, products, conversions, reservations, rollback, and persisted allocations must not overflow, truncate, leak, or be charged twice. Five structured-DRA allocator defects fixed and merged for Kubernetes v1.37 — driver/pool cache isolation, reliable backtracking rollback, no double-charge on persisted shared devices, unusable `validRange` rejection, and unrepresentable-capacity rejection — then the same variant search carried across Kueue, Volcano, CDI, and vendor DRA drivers (Intel QAT, Google TPU, IBM Power, AMD ROCm).
[k8s #140435](https://github.com/kubernetes/kubernetes/pull/140435) · [#140431](https://github.com/kubernetes/kubernetes/pull/140431) · [#140437](https://github.com/kubernetes/kubernetes/pull/140437) · [#140666](https://github.com/kubernetes/kubernetes/pull/140666) · [#140442](https://github.com/kubernetes/kubernetes/pull/140442)

**Async lifecycle & observability.** OpenTelemetry C++ exporters reviewed by lifecycle contract: an operation must not outlive its owner, miss its completion notification, or be settled zero or two times under cancellation and shutdown races.
[HttpServer use-after-free #4289](https://github.com/open-telemetry/opentelemetry-cpp/pull/4289) · [ES exporter lost wakeup #4298](https://github.com/open-telemetry/opentelemetry-cpp/pull/4298) · [curl exactly-once completion #4363](https://github.com/open-telemetry/opentelemetry-cpp/pull/4363)

**Transactional cloud-native telecom.** NTN control paths in OCUDU treated as one transaction rather than isolated bugs — a SIB19 update audited end to end across coroutine lifetimes, queue backpressure, validation, rollback, timing boundaries, and system-information assembly. Carried through Nephio governance and upstream merge requests.

Full failure analyses, patches, tests, and review threads are in the [open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/); active work is tracked through my [open pull requests](https://github.com/search?q=is%3Apr+author%3Athc1006+is%3Aopen&type=pullrequests).

### Verified credential

**AMD ROCm™ Certified Associate** — AMD. ROCm software application development, optimization, and deployment of AI/HPC workloads on AMD Instinct GPUs.
[Verify on Credly](https://www.credly.com/badges/4c7dbe32-9ee7-4c15-8919-9f4dccd81383) · [related ROCm upstream work](https://github.com/ROCm/k8s-gpu-dra-driver/pulls?q=is%3Apr+author%3Athc1006)

### Community

I serve on the Nephio Technical Steering Committee, maintain M5Stack platforms in upstream Zephyr, and organize the *O-RAN in B5G/6G* track at COSCUP. I give technical talks in Taiwanese (Tâi-gí), and am building bilingual, review-driven contribution walkthroughs to lower the barrier from using cloud-native software to contributing upstream. Completed **LFC102: Inclusive Open Source Community Orientation** (July 2026).

---

<div align="center">

[Website](https://people.cs.nycu.edu.tw/~hctsai1006/) ·
[Publications](https://people.cs.nycu.edu.tw/~hctsai1006/publications/) ·
[Honors](https://people.cs.nycu.edu.tw/~hctsai1006/honors/) ·
[ORCID](https://orcid.org/0000-0001-7421-8027) ·
[LinkedIn](https://linkedin.com/in/thc1006) ·
[LFX](https://openprofile.dev/profile/thc1006) ·
[Credly](https://www.credly.com/users/hsiu-chi-tsai) ·
hctsai@linux.com

</div>

<sub>Research assistant at National Yang Ming Chiao Tung University, Taiwan. Raised in a fishing village in Dapeng Bay, Pingtung. I care about making technical communities easier to enter, especially for people who do not start with an established professional network or English-first resources.</sub>
