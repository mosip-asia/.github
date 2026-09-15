# 🏷️ MOSIP Asia Standard Label Taxonomy

This document defines the standardized GitHub label hierarchy across all repositories in the `mosip-asia` organization.

---

## 1. 🏛️ Pillar Labels (Prefix: `pillar:`)
Identifies which of the 4 core organizational pillars owns the item:

| Label | Color | Description |
|---|---|---|
| `pillar:platform` | `#0E8A16` (Green) | Pillar 1: DPI Platform, Core Identity, Trust Framework, Cloud IaC |
| `pillar:facepad` | `#1D76DB` (Blue) | Pillar 2: Biometrics R&D, ISO 30107-3 PAD, Datasets & Liveness Models |
| `pillar:ai` | `#5319E7` (Purple) | Pillar 3: AI Assistant, Copilots, Document RAG, Multi-Agent Systems |
| `pillar:apps` | `#FBCA04` (Yellow) | Pillar 4: Digital Applications, Wallets, Portals & Client Projects |

---

## 2. 🔍 Work Type Labels (Prefix: `type:`)
Identifies the nature of the issue or pull request:

| Label | Color | Description |
|---|---|---|
| `type:rfc` | `#7057FF` | Architectural proposal, design specification, or schema RFC |
| `type:research` | `#D93F0B` | Time-boxed scientific investigation, benchmark, or ML evaluation |
| `type:feature` | `#A2EEEF` | New functional capability or user story implementation |
| `type:bug` | `#D73A4A` | Software defect, probe timeout, or broken deployment pipeline |
| `type:milestone` | `#006B75` | Official grant WBS milestone, release gate, or contractor sign-off |
| `type:docs` | `#0075CA` | Runbooks, user guides, or technical documentation updates |
| `type:infra` | `#BFDADC` | Terraform modules, Helm chart packaging, or CI/CD runner workflows |

---

## 3. 🎯 Priority & Status Labels
Tracks urgency and workflow state across project boards:

| Label | Color | Description |
|---|---|---|
| `priority:critical` | `#B60205` | Blocks critical path milestone, security vulnerability, or broken build |
| `priority:high` | `#D93F0B` | Must be delivered in the active sprint |
| `priority:medium` | `#FBCA04` | Standard scheduled sprint backlog item |
| `priority:low` | `#FEF2C0` | Nice-to-have optimization or polish |
| `status:blocked` | `#B60205` | Work cannot proceed due to external or cross-track blocker |
| `status:in-review` | `#0052CC` | Pull request under peer review |
| `status:verified` | `#0E8A16` | Automated smoke test or DoD verified |
