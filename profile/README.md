<div align="center">

<img src="https://raw.githubusercontent.com/NTIC-Solution/.github/main/profile/banner.svg" width="100%" alt="NTIC Solution — Cybersecurity · Infrastructure · Automation · DevSecOps">

<br><br>

[![Website](https://img.shields.io/badge/nticsolution.com-0A66C2?style=for-the-badge)](https://nticsolution.com)
[![Email](https://img.shields.io/badge/support%40nticsolution.com-1E293B?style=for-the-badge)](mailto:support@nticsolution.com)
![Montréal, Québec](https://img.shields.io/badge/Montr%C3%A9al%2C%20Qu%C3%A9bec-C1121F?style=for-the-badge)

![GitOps](https://img.shields.io/badge/GitOps-Argo%20CD-EF7B4D?style=flat-square&labelColor=0D1117&logo=argo&logoColor=white)
![IaC](https://img.shields.io/badge/IaC-Terraform%20%2B%20Ansible-844FBA?style=flat-square&labelColor=0D1117&logo=terraform&logoColor=white)
![Access](https://img.shields.io/badge/Access-Zero%20Trust-F38020?style=flat-square&labelColor=0D1117&logo=cloudflare&logoColor=white)
![Secrets](https://img.shields.io/badge/Secrets-1Password-0094F5?style=flat-square&labelColor=0D1117&logo=1password&logoColor=white)
![Runtime](https://img.shields.io/badge/Runtime-Kubernetes%20%28k3s%29-326CE5?style=flat-square&labelColor=0D1117&logo=kubernetes&logoColor=white)

<br>

**Secure, reproducible infrastructure — declared in Git, delivered by GitOps, operated with discipline.**

</div>

---

## About

NTIC Solution is a Montréal-based technology and cybersecurity firm. We design, secure and operate environments where **everything is code**: servers, networks and workloads are declared in Git, deployed through GitOps, and rebuilt from source rather than patched by hand.

## What we do

| 🛡️ Cybersecurity | 🏗️ Infrastructure | ⚙️ Platform engineering | 🤖 Automation |
| :-- | :-- | :-- | :-- |
| Security hardening<br>Zero Trust access<br>Least-privilege identity | Network architecture<br>Bare-metal virtualization<br>Hybrid cloud | Infrastructure as Code<br>GitOps delivery<br>Kubernetes operations | Workflow orchestration<br>DevSecOps pipelines<br>Operational runbooks |

## How we build

| Principle | In practice |
| :-- | :-- |
| **Everything as code** | If it isn't declared in a repository, it doesn't exist. Terraform builds, Ansible configures, Argo CD runs. |
| **GitOps by default** | The cluster converges to Git. Changes land by commit — never by click or `kubectl edit`. |
| **Reproducible by design** | Any environment can be rebuilt from Git plus the secret store. |
| **One home for secrets** | 1Password is the system of record. An exposed secret is a burned secret: rotate first. |
| **Least privilege** | Machines get narrowly scoped identities (service principals, GitHub Apps). Elevated rights are granted, used and revoked in the same session. |
| **Read-only first** | Every change starts with an inventory — `list`, `show`, `plan` — before anything is mutated. |
| **One change, one commit** | Every change, version bumps included, is its own commit and its own rollback point. |

## Stack

| Layer | Technologies |
| :-- | :-- |
| **Hosting & virtualization** | ![OVHcloud](https://img.shields.io/badge/OVHcloud-123F6D?style=for-the-badge&logo=ovh&logoColor=white) ![Proxmox VE](https://img.shields.io/badge/Proxmox%20VE-E57000?style=for-the-badge&logo=proxmox&logoColor=white) ![Debian](https://img.shields.io/badge/Debian-A81D33?style=for-the-badge&logo=debian&logoColor=white) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) |
| **Network & access** | ![OPNsense](https://img.shields.io/badge/OPNsense-D94F00?style=for-the-badge&logo=opnsense&logoColor=white) ![Cloudflare Zero Trust](https://img.shields.io/badge/Cloudflare%20Zero%20Trust-F38020?style=for-the-badge&logo=cloudflare&logoColor=white) |
| **Provisioning & configuration** | ![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=for-the-badge&logo=terraform&logoColor=white) ![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white) ![Azure Blob](https://img.shields.io/badge/Azure%20Blob%20%C2%B7%20remote%20state-0078D4?style=for-the-badge) |
| **Orchestration & delivery** | ![K3s](https://img.shields.io/badge/K3s-FFC61C?style=for-the-badge&logo=k3s&logoColor=black) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white) ![Argo CD](https://img.shields.io/badge/Argo%20CD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white) ![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white) |
| **Workloads & data** | ![n8n](https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL%20%C2%B7%20CloudNativePG-4169E1?style=for-the-badge&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-FF4438?style=for-the-badge&logo=redis&logoColor=white) |
| **Identity & secrets** | ![1Password](https://img.shields.io/badge/1Password-0094F5?style=for-the-badge&logo=1password&logoColor=white) ![GitHub Apps](https://img.shields.io/badge/GitHub%20Apps-181717?style=for-the-badge&logo=github&logoColor=white) |

## Field notes

- **Healthy is not reconciling.** A workload can stay green while its GitOps control plane is frozen. Watch sync status and repository connectivity, not just pod health.
- **Prefer GitHub Apps over deploy keys.** Organization policy can silently disable a deploy key; an App issues short-lived, scoped tokens and survives policy changes.
- **Visibility is not access.** Seeing a cloud subscription doesn't mean holding a role on it. Review role assignments when people leave — before deleting the account.
- **Respect the lock.** Remote state locking exists for a reason: answer the prompt instead of hitting <kbd>Ctrl</kbd>+<kbd>C</kbd>.

## Now building

- ✅ Terraform remote state with lease locking and keyless (Entra ID) authentication
- ✅ Argo CD authenticated as a GitHub App over HTTPS
- 🔄 App-of-apps — every Argo CD Application declared in Git
- 🔄 Second bare-metal host, with its firewall provisioned by Terraform from day one
- 🔜 Alerting on stalled reconciliation
- 🔜 Declarative secrets with External Secrets Operator + 1Password

## Security

Found a vulnerability in something we operate? Please report it privately to **[support@nticsolution.com](mailto:support@nticsolution.com)** instead of opening a public issue.

---

<div align="center">

**NTIC Solution** · Montréal, Québec, Canada<br>
[nticsolution.com](https://nticsolution.com) · [support@nticsolution.com](mailto:support@nticsolution.com)

</div>
