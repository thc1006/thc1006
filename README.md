<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

**Kubernetes scheduling and quota accounting · Observability · Cloud-native telecom**

Member of the Kubernetes GitHub organization.
Nephio Technical Steering Committee member (LF Networking).
Maintainer of M5Stack Platforms in upstream Zephyr.
Research assistant at National Yang Ming Chiao Tung University, Taiwan.

</div>

|  |  |
| --- | --- |
| **CNCF DevStats** | [**2,000**](https://devstats.cluster.fun/?user=thc1006) |
| **Merged upstream** | **119 pull requests across 52 projects.** 94 of them in 40 CNCF-hosted and Kubernetes-ecosystem repositories. |
| **Kubernetes** | GitHub **org member** ([kubernetes/org#6498](https://github.com/kubernetes/org/issues/6498)) |
| **Governance** | Nephio **TSC member**, LF Networking ([roster](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667)) |
| **Maintainer** | **M5Stack Platforms** in upstream Zephyr, `status: maintained` ([MAINTAINERS.yml](https://github.com/zephyrproject-rtos/zephyr/blob/main/MAINTAINERS.yml)) |
| **Community** | Organizer of the *O-RAN in B5G/6G* track at COSCUP · I give technical talks in Taiwanese (Tâi-gí) |

Every merged contribution, listed and linked: **[open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

<sub>The CNCF DevStats score updates daily via GitHub Actions; other figures as of July 2026.</sub>

### Recent work

I focus on correctness in Kubernetes Dynamic Resource Allocation (DRA), particularly quota arithmetic, allocator state management, and device lifecycle handling. A quota-accounting audit began with an `int64` overflow in Kueue ([`#12896`](https://github.com/kubernetes-sigs/kueue/issues/12896)). It led to a four-PR Kueue hardening series ([`#12897`](https://github.com/kubernetes-sigs/kueue/pull/12897), [`#12909`](https://github.com/kubernetes-sigs/kueue/pull/12909), [`#12945`](https://github.com/kubernetes-sigs/kueue/pull/12945), and [`#12954`](https://github.com/kubernetes-sigs/kueue/pull/12954)), followed by a corresponding overflow fix in Volcano ([`#5621`](https://github.com/volcano-sh/volcano/pull/5621)).

In Kubernetes core, I identified and fixed five defects in the structured DRA allocator. All five fixes were merged for Kubernetes v1.37 with release notes: prevented cross-driver collisions by scoping shared-counter caches to both driver and pool ([`#140435`](https://github.com/kubernetes/kubernetes/pull/140435)); made candidate rejection and backtracking reliably roll back reserved allocator state ([`#140431`](https://github.com/kubernetes/kubernetes/pull/140431)); stopped counters from being charged twice for persisted shared-device allocations ([`#140437`](https://github.com/kubernetes/kubernetes/pull/140437)); rejected unusable `validRange` bounds before they could cause divide-by-zero or incorrect validation ([`#140666`](https://github.com/kubernetes/kubernetes/pull/140666)); rejected unrepresentable capacity requests instead of accepting allocations that a device could not satisfy ([`#140442`](https://github.com/kubernetes/kubernetes/pull/140442)).

Related upstream fixes include a claim-unprepare device leak in Intel's QAT DRA driver ([`#74`](https://github.com/intel/intel-resource-drivers-for-kubernetes/pull/74)) and a slice-bounds panic in the CNCF Container Device Interface parser ([`#321`](https://github.com/cncf-tags/container-device-interface/pull/321)). Open work: a nil-dereference fix for KubeVirt's mediated-device builders ([`#18431`](https://github.com/kubevirt/kubevirt/pull/18431)) and an unlimited-quota sentinel bug in KAI-Scheduler's parent/child quota validation ([`#1881`](https://github.com/kai-scheduler/KAI-Scheduler/issues/1881)). Additional work is tracked through my [open pull requests](https://github.com/search?q=is%3Apr+author%3Athc1006+is%3Aopen&type=pullrequests).

### Community focus

My next focus is lowering the barrier from using cloud-native software to contributing upstream: newcomer sessions in Mandarin and Taiwanese (Tâi-gí), together with bilingual contribution walkthroughs based on real review discussions. I completed **LFC102: Inclusive Open Source Community Orientation** in July 2026.

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

<sub>Raised in a fishing village in Dapeng Bay, Pingtung. I care about making technical communities easier to enter, especially for people who do not start with an established professional network or English-first resources.</sub>
