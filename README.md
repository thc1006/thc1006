<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

**Kubernetes scheduling and quota accounting · Observability · Cloud-native telecom**

</div>

|  |  |
| --- | --- |
| **CNCF DevStats** | [**2,962**](https://devstats.cluster.fun/?user=thc1006) |
| **Merged upstream** | **202 pull requests across 61 projects.** 153 of them in 42 CNCF-hosted and Kubernetes-ecosystem repositories. |
| **Kubernetes** | [**GitHub org member**](https://github.com/kubernetes/org/issues/6498) |
| **Governance** | [**Nephio TSC member**](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667), LF Networking |
| **OpenTelemetry** | [**GitHub org member**](https://github.com/open-telemetry/community/issues/3597) |
| **Maintainer** | [**M5Stack Platforms**](https://github.com/zephyrproject-rtos/zephyr/blob/main/MAINTAINERS.yml) in upstream Zephyr, `status: maintained` |
| **Community** | Organizer of the *O-RAN in B5G/6G* track at COSCUP · I give technical talks in Taiwanese (Tâi-gí) |

Every merged contribution, listed and linked: **[open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

<sub>The CNCF DevStats score refreshes automatically via GitHub Actions; other figures as of August 2026.</sub>

### Recent work

I focus on correctness in Kubernetes Dynamic Resource Allocation (DRA), particularly quota arithmetic, allocator state management, and device lifecycle handling. A quota-accounting audit began with an `int64` overflow in Kueue ([`#12896`](https://github.com/kubernetes-sigs/kueue/issues/12896)). It led to a four-PR Kueue hardening series ([`#12897`](https://github.com/kubernetes-sigs/kueue/pull/12897), [`#12909`](https://github.com/kubernetes-sigs/kueue/pull/12909), [`#12945`](https://github.com/kubernetes-sigs/kueue/pull/12945), and [`#12954`](https://github.com/kubernetes-sigs/kueue/pull/12954)), followed by a corresponding overflow fix in Volcano ([`#5621`](https://github.com/volcano-sh/volcano/pull/5621)).

In Kubernetes core, I identified and fixed five defects in the structured DRA allocator. All five fixes were merged for Kubernetes v1.37 with release notes: prevented cross-driver collisions by scoping shared-counter caches to both driver and pool ([`#140435`](https://github.com/kubernetes/kubernetes/pull/140435)); made candidate rejection and backtracking reliably roll back reserved allocator state ([`#140431`](https://github.com/kubernetes/kubernetes/pull/140431)); stopped counters from being charged twice for persisted shared-device allocations ([`#140437`](https://github.com/kubernetes/kubernetes/pull/140437)); rejected unusable `validRange` bounds before they could cause divide-by-zero or incorrect validation ([`#140666`](https://github.com/kubernetes/kubernetes/pull/140666)); rejected unrepresentable capacity requests instead of accepting allocations that a device could not satisfy ([`#140442`](https://github.com/kubernetes/kubernetes/pull/140442)).

I then ran the same variant analysis across vendor DRA drivers. A `ResourceClaim` can be satisfied by devices from more than one driver, so each driver's kubelet plugin must skip the allocation results it does not own; the reference driver (`kubernetes-sigs/dra-example-driver`) does exactly that, with a comment explaining why. Several vendors kept that guard on the config path they had copied from the reference but dropped it on their prepare path, so a pod whose claim mixes two drivers has a valid allocation rejected. I reported and fixed it in Google's TPU driver ([`#25`](https://github.com/kubernetes-sigs/dra-driver-google-tpu/pull/25)) and IBM's Power driver ([`#323`](https://github.com/IBM/power-dra-driver/pull/323)), and reported the same in IBM's Spyre driver ([`#59`](https://github.com/ibm-aiu/dra-driver-spyre/issues/59)); the SR-IOV driver ([`#136`](https://github.com/k8snetworkplumbingwg/dra-driver-sriov/issues/136)) drops the equivalent guard on its status-update path. The correct pattern already ships in the reference and still gets dropped when the loop is hand-rolled, so the fix belongs upstream: a shared helper or conformance check in `k8s.io/dynamic-resource-allocation` rather than more per-driver documentation.

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

<sub>Research assistant at National Yang Ming Chiao Tung University, Taiwan. Raised in a fishing village in Dapeng Bay, Pingtung. I care about making technical communities easier to enter, especially for people who do not start with an established professional network or English-first resources.</sub>
