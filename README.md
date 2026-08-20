<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

**upstream systems engineer. i work on Kubernetes correctness, observability, and cloud native telecom.**

my way is simple. i find one bug, then i make it into a rule i can use again, and i go check other projects if they have the same bug. after i fix it i add a test and send it to upstream.

</div>

|  |  |
| --- | --- |
| **Merged upstream** | **245 pull requests in 71 projects.** 171 of them are in 46 CNCF and Kubernetes ecosystem repos. |
| **CNCF related contributions** | [**3,782**](https://devstats.cluster.fun/?user=thc1006) |
| **Kubernetes** | [**GitHub org member**](https://github.com/kubernetes/org/issues/6498) |
| **Governance** | [**Nephio TSC member**](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667), LF Networking |
| **OpenTelemetry** | [**GitHub org member**](https://github.com/open-telemetry/community/issues/3597) |
| **Maintainer** | [**M5Stack Platforms**](https://github.com/zephyrproject-rtos/zephyr/blob/main/MAINTAINERS.yml) in upstream Zephyr, `status: maintained` |

every merged PR is listed and linked here: **[open source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

<sub>the CNCF number update by itself from CNCF DevStats GithubIDContributions API. it is a count of contributions, not a score. the other numbers are my authored, merged, public upstream PR, and i check them again in August 2026.</sub>

### what i work on

most of my work is Kubernetes DRA correctness. i read the scheduler and device allocation code and i check the math and the state: sum, product, convert, reserve, rollback, and saved allocation. they should not overflow, truncate, leak, or charge twice. i find and fix five bug of this kind in the Kubernetes v1.37 allocator: driver and pool cache mix together, rollback not clean after backtrack, double charge on a saved shared device, bad `validRange` not reject, and too big capacity not reject. after that i use the same check on other project too, like Kueue, Volcano, CDI, and vendor DRA driver from Intel QAT, Google TPU, IBM Power, and AMD ROCm.
[k8s #140435](https://github.com/kubernetes/kubernetes/pull/140435) · [#140431](https://github.com/kubernetes/kubernetes/pull/140431) · [#140437](https://github.com/kubernetes/kubernetes/pull/140437) · [#140666](https://github.com/kubernetes/kubernetes/pull/140666) · [#140442](https://github.com/kubernetes/kubernetes/pull/140442)

for observability i review OpenTelemetry C++ exporter by its lifecycle. one operation should not live longer than its owner, should not miss the finish signal, and should not settle zero time or two time when cancel and shutdown race together.
[HttpServer use after free #4289](https://github.com/open-telemetry/opentelemetry-cpp/pull/4289) · [ES exporter lost wakeup #4298](https://github.com/open-telemetry/opentelemetry-cpp/pull/4298) · [curl settle one time #4363](https://github.com/open-telemetry/opentelemetry-cpp/pull/4363)

for telecom i work on the OCUDU NTN control path. i treat one SIB19 update as one transaction, not many small bug. i check it from start to end: coroutine lifetime, queue backpressure, validation, rollback, timing boundary, and system information assembly. this work go through Nephio governance and upstream merge request.

the full analysis, the patch, the test and the review talk are all in my [open source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/). what i do right now is in my [open pull requests](https://github.com/search?q=is%3Apr+author%3Athc1006+is%3Aopen&type=pullrequests).

### one certificate i have

**AMD ROCm™ Certified Associate**, from AMD. it is about ROCm software develop, optimize, and deploy for AI and HPC work on AMD Instinct GPU.
[verify on Credly](https://www.credly.com/badges/4c7dbe32-9ee7-4c15-8919-9f4dccd81383) · [my ROCm upstream work](https://github.com/ROCm/k8s-gpu-dra-driver/pulls?q=is%3Apr+author%3Athc1006)

### community

i am on the Nephio Technical Steering Committee, i maintain the M5Stack platform in upstream Zephyr, and i run the *O-RAN in B5G/6G* track in COSCUP. i give tech talk in Taiwanese. i also make bilingual walkthrough from real review talk, because i want the step from use to contribute more easy. i finish **LFC102: Inclusive Open Source Community Orientation** in July 2026.

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

<sub>i am a research assistant in National Yang Ming Chiao Tung University, Taiwan. i grow up in a small fishing village in Dapeng Bay, Pingtung. i care about make the technical community easy to enter, specially for people who do not start with a big network or English first resource.</sub>
