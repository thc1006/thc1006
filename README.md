<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

**Upstream systems engineer. I work on Kubernetes correctness, observability, and cloud native telecom.**

My way is simple. I find one bug, then I turn it into a rule I can reuse, and I check other projects for the same bug. After I fix it, I add a test and send it upstream.

</div>

|  |  |
| --- | --- |
| **Merged upstream** | **245 pull requests in 71 projects.** 171 of them are in 46 CNCF and Kubernetes ecosystem repos. |
| **CNCF related contributions** | [**3,800**](https://devstats.cluster.fun/?user=thc1006) |
| **Kubernetes** | [**GitHub org member**](https://github.com/kubernetes/org/issues/6498) |
| **Governance** | [**Nephio TSC member**](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667), LF Networking |
| **OpenTelemetry** | [**GitHub org member**](https://github.com/open-telemetry/community/issues/3597) |
| **Maintainer** | [**M5Stack Platforms**](https://github.com/zephyrproject-rtos/zephyr/blob/main/MAINTAINERS.yml) in upstream Zephyr, `status: maintained` |

Every merged PR is listed and linked here: **[open source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

<sub>The CNCF number updates by itself from the CNCF DevStats GithubIDContributions API. It is a count of contributions, not a score. The other numbers are my authored, merged, public upstream PRs, last checked in August 2026.</sub>

### What I work on

Most of my work is Kubernetes DRA correctness. I read the scheduler and device allocation code, and I check the math and the state: sums, products, conversions, reservations, rollback, and saved allocations. They should not overflow, truncate, leak, or charge twice. I found and fixed five bugs of this kind in the Kubernetes v1.37 allocator: the driver and pool cache mixed together, rollback was not clean after backtracking, a saved shared device was charged twice, a bad `validRange` was not rejected, and a capacity too large to serve was not rejected. After that I ran the same check on other projects too, like Kueue, Volcano, CDI, and vendor DRA drivers from Intel QAT, Google TPU, IBM Power, and AMD ROCm.
[k8s #140435](https://github.com/kubernetes/kubernetes/pull/140435) · [#140431](https://github.com/kubernetes/kubernetes/pull/140431) · [#140437](https://github.com/kubernetes/kubernetes/pull/140437) · [#140666](https://github.com/kubernetes/kubernetes/pull/140666) · [#140442](https://github.com/kubernetes/kubernetes/pull/140442)

For observability I review OpenTelemetry C++ exporters by their lifecycle. One operation should not live longer than its owner, should not miss the finish signal, and should not settle zero times or two times when cancel and shutdown race together.
[HttpServer use after free #4289](https://github.com/open-telemetry/opentelemetry-cpp/pull/4289) · [ES exporter lost wakeup #4298](https://github.com/open-telemetry/opentelemetry-cpp/pull/4298) · [curl settle one time #4363](https://github.com/open-telemetry/opentelemetry-cpp/pull/4363)

For telecom I work on the OCUDU NTN control path. I treat one SIB19 update as one transaction, not many small bugs. I check it from start to end: coroutine lifetimes, queue backpressure, validation, rollback, timing boundaries, and system information assembly. This work goes through Nephio governance and upstream merge requests.

The full analysis, the patch, the test, and the review discussion are all in my [open source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/). What I do right now is in my [open pull requests](https://github.com/search?q=is%3Apr+author%3Athc1006+is%3Aopen&type=pullrequests).

### One certificate I have

**AMD ROCm™ Certified Associate**, from AMD. It is about developing, optimizing, and deploying ROCm software for AI and HPC work on AMD Instinct GPUs.
[verify on Credly](https://www.credly.com/badges/4c7dbe32-9ee7-4c15-8919-9f4dccd81383) · [my ROCm upstream work](https://github.com/ROCm/k8s-gpu-dra-driver/pulls?q=is%3Apr+author%3Athc1006)

### Community

I am on the Nephio Technical Steering Committee, I maintain the M5Stack platform in upstream Zephyr, and I run the *O-RAN in B5G/6G* track at COSCUP. I give tech talks in Taiwanese. I also make bilingual walkthroughs from real review discussions, because I want to make the step from using to contributing easier. I finished **LFC102: Inclusive Open Source Community Orientation** in July 2026.

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

<sub>I am a research assistant at National Yang Ming Chiao Tung University, Taiwan. I grew up in a small fishing village in Dapeng Bay, Pingtung. I care about making the technical community easier to enter, especially for people who do not start with a big network or resources in English.</sub>
