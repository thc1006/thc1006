<div align="center">

# Hsiu-Chi Tsai · 蔡秀吉

**Kubernetes scheduling and quota accounting · Observability · Cloud-native telecom**

Nephio Technical Steering Committee member (LF Networking).
Maintainer of M5Stack Platforms in upstream Zephyr.
Research assistant at National Yang Ming Chiao Tung University, Taiwan.

</div>

|  |  |
| --- | --- |
| **CNCF DevStats** | [**1,779**](https://devstats.cluster.fun/?user=thc1006) |
| **Merged upstream** | **98 pull requests across 46 projects.** 79 of them in 40 CNCF-hosted and Kubernetes-ecosystem repositories. |
| **Governance** | Nephio **TSC member**, LF Networking ([roster](https://lf-nephio.atlassian.net/wiki/spaces/HOME/pages/152305667)) |
| **Maintainer** | **M5Stack Platforms** in upstream Zephyr, `status: maintained` ([MAINTAINERS.yml](https://github.com/zephyrproject-rtos/zephyr/blob/main/MAINTAINERS.yml)) |
| **Community** | Organizer of the *O-RAN in B5G/6G* track at COSCUP · I give technical talks in Taiwanese (Tâi-gí) |

Every merged contribution, listed and linked: **[open-source portfolio](https://people.cs.nycu.edu.tw/~hctsai1006/open-source/)**

<sub>Figures as of 13 July 2026. The DevStats link is live and will be ahead of the number above.</sub>

### Recent work

I audit Dynamic Resource Allocation for arithmetic and lifecycle bugs. It began with an `int64` overflow in quota accounting, which I reported in [`kueue#12896`](https://github.com/kubernetes-sigs/kueue/issues/12896), fixed across four merged pull requests, then found and fixed in [Volcano](https://github.com/volcano-sh/volcano/pull/5621).

That audit is now open across the ecosystem: overflow and panic bugs in Kubernetes core DRA ([3 pull requests](https://github.com/kubernetes/kubernetes/pulls?q=is%3Apr+author%3Athc1006), [5 issues](https://github.com/kubernetes/kubernetes/issues?q=is%3Aissue+author%3Athc1006)), a slice-bounds panic in CNCF [container-device-interface](https://github.com/cncf-tags/container-device-interface/pull/321), a nil dereference in [KubeVirt](https://github.com/kubevirt/kubevirt/pull/18431), and quota-accounting problems in [KAI-Scheduler](https://github.com/kai-scheduler/KAI-Scheduler/issues/1881). These are under review and not yet merged.

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
