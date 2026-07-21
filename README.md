<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

**Kubernetes scheduling and quota accounting · Observability · Cloud-native telecom**

Nephio Technical Steering Committee member (LF Networking).
Maintainer of M5Stack Platforms in upstream Zephyr.
Research assistant at National Yang Ming Chiao Tung University, Taiwan.

</div>

|  |  |
| --- | --- |
| **CNCF DevStats** | [**1,918**](https://devstats.cluster.fun/?user=thc1006) |
| **Merged upstream** | **114 pull requests across 50 projects.** 91 of them in 42 CNCF-hosted and Kubernetes-ecosystem repositories. |
| **Governance** | Nephio **TSC member**, LF Networking ([roster](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667)) |
| **Maintainer** | **M5Stack Platforms** in upstream Zephyr, `status: maintained` ([MAINTAINERS.yml](https://github.com/zephyrproject-rtos/zephyr/blob/main/MAINTAINERS.yml)) |
| **Community** | Organizer of the *O-RAN in B5G/6G* track at COSCUP · I give technical talks in Taiwanese (Tâi-gí) |

Every merged contribution, listed and linked: **[open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

<sub>The CNCF DevStats score updates daily via GitHub Actions; other figures as of July 2026.</sub>

### Recent work

I audit Dynamic Resource Allocation for arithmetic and lifecycle bugs. It began with an `int64` overflow in quota accounting, which I reported in [`kueue#12896`](https://github.com/kubernetes-sigs/kueue/issues/12896), fixed across four merged pull requests, then found and fixed in [Volcano](https://github.com/volcano-sh/volcano/pull/5621).

The audit has since reached the Kubernetes core structured allocator, where four fixes have merged with release notes: a counter-cache collision between DRA drivers ([`#140434`](https://github.com/kubernetes/kubernetes/issues/140434) fixed in [`#140435`](https://github.com/kubernetes/kubernetes/pull/140435)), a reserved-state leak on the reject/backtrack path ([`#140436`](https://github.com/kubernetes/kubernetes/issues/140436) fixed in [`#140431`](https://github.com/kubernetes/kubernetes/pull/140431)), a shared counter double-counted for a persisted device ([`#140433`](https://github.com/kubernetes/kubernetes/issues/140433) fixed in [`#140437`](https://github.com/kubernetes/kubernetes/pull/140437)), and a divide-by-zero on a `validRange.step` that slips past its `Sign()` guard through `Value()` truncation ([`#140472`](https://github.com/kubernetes/kubernetes/issues/140472) fixed in [`#140666`](https://github.com/kubernetes/kubernetes/pull/140666)). The same class of bug reached Intel's QAT DRA driver, a device leak on the claim-unprepare path ([`#73`](https://github.com/intel/intel-resource-drivers-for-kubernetes/issues/73) fixed in [`#74`](https://github.com/intel/intel-resource-drivers-for-kubernetes/pull/74)), and CNCF's [container-device-interface](https://github.com/cncf-tags/container-device-interface/pull/321), a slice-bounds panic on a single-character vendor name.

Still under review: two more core pull requests on the same consumable-capacity arithmetic, a nil dereference in [KubeVirt](https://github.com/kubevirt/kubevirt/pull/18431)'s host-device builder, and quota-accounting problems in [KAI-Scheduler](https://github.com/kai-scheduler/KAI-Scheduler/issues/1881).

### Next

I want to help more people cross from *using* cloud native software to *contributing* to it: newcomer sessions in Mandarin and Taiwanese, and bilingual contribution walkthroughs drawn from real review threads. I completed **LFC102 (Inclusive Open Source Community Orientation)** in July 2026.

---

[Website](https://people.cs.nycu.edu.tw/~hctsai1006/) ·
[Publications](https://people.cs.nycu.edu.tw/~hctsai1006/publications/) ·
[Honors](https://people.cs.nycu.edu.tw/~hctsai1006/honors/) ·
[ORCID](https://orcid.org/0000-0001-7421-8027) ·
[LinkedIn](https://linkedin.com/in/thc1006) ·
[LFX](https://openprofile.dev/profile/thc1006) ·
[Credly](https://www.credly.com/users/hsiu-chi-tsai) ·
hctsai@linux.com

<sub>Raised in a fishing village in Dapeng Bay, Pingtung. I care about making technical communities easier to enter, especially for people who do not start with an established professional network or English-first resources.</sub>
