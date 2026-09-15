# 📘 MOSIP Asia Engineering Operating Handbook & Contributing Guidelines

> **The Authoritative Governance Guide for all Engineers, Researchers, and Contributors across `mosip-asia`.**

---

## 1. 🌟 Core Engineering Principles

Every engineer, architect, and researcher working in `mosip-asia` adheres to four foundational tenets:

1. **Pure Upstream Parity (No Code Forks):**
   - We do not modify official MOSIP or Inji Docker images or chart templates.
   - Upstream services are headless consumers configured strictly through declarative values, ConfigMaps, and Terraform `.tfvars`.
2. **Decoupled Black-Box Contracts:**
   - Teams collaborate via stable interfaces (REST APIs, OIDC, OID4VCI/OID4VP protocols, and tagged OCI container images).
   - Platform engineers do not need to understand PyTorch model code; ML researchers do not need to manage Kubernetes or Terraform.
3. **Docs-as-Code (RFCs & Architecture Decisions):**
   - Research spikes, architecture designs, and schema proposals are written in Markdown and reviewed through Pull Requests.
   - No architectural decisions are made verbally or lost in unversioned documents.
4. **Zero-Leak Security Guardrail:**
   - Never commit `.env`, `.tfvars`, private keys, or API tokens to git.
   - All environments must support disposable, automated destruction ($0 idle waste).

---

## 2. 🔄 The Issue-to-PR Engineering Workflow

Work across all `mosip-asia` repositories strictly follows the **4-Stage Issue-to-PR Lifecycle**:

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        THE 4-STAGE ISSUE-TO-PR LIFECYCLE                               │
├────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                        │
│  1. 📝 ISSUE (The "What" & "Why")                                                      │
│     • Must be filed using one of the official issue templates:                         │
│       - Feature / RFC                                                                  │
│       - Research Spike                                                                 │
│       - Bug / Defect                                                                   │
│       - Management Milestone                                                           │
│     • Must include clear, testable Acceptance Criteria.                                │
│                                                                                        │
│  2. 🌿 BRANCH (The "How")                                                              │
│     • Created from `main` or `develop` using standard naming:                          │
│       feat/<track-or-pillar>-<short-description>                                       │
│       research/<topic-description>                                                     │
│       fix/<issue-number>-<short-description>                                           │
│                                                                                        │
│  3. 📦 PULL REQUEST (The "Proof")                                                      │
│     • Uses the organization Pull Request template.                                     │
│     • Must include: `Closes #<IssueNumber>` in the description.                        │
│     • Must include: Concrete Verification Proof (Smoke test output, ML metrics, UI).   │
│                                                                                        │
│  4. 🎯 VERIFICATION & MERGE                                                            │
│     • Peer review approval required.                                                   │
│     • Merge closes the issue and automatically updates the Project Board.              │
│                                                                                        │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

> [!IMPORTANT]
> **The Golden Rule:** If there is no Pull Request with proof of verification, the work is not complete. Direct pushes to `main` are strictly blocked.

---

## 3. 🏷️ Repository Naming Taxonomy

To ensure navigability across our Digital Public Infrastructure Center, all repositories are named with standard pillar prefixes:

| Prefix | Pillar | Scope & Focus |
|---|---|---|
| **`dpi-*`** | Platform & Sandbox | Core MOSIP identity, Inji trust framework, Kubernetes infrastructure, and cloud GitOps. |
| **`facepad-*`** | Biometric R&D | ISO/IEC 30107-3 presentation attack detection, liveness datasets, ML models, and red-teaming. |
| **`ai-*`** | AI Assistant & Agents | Identity copilots, specification RAG engines, multi-agent frameworks, and developer tooling. |
| **`app-*`** | Digital Applications | Citizen Web Wallet PWA, hackathon submission portals, SDK starter kits, and client projects. |
| **`docs-*`** | Technical Specifications | Centralized architecture blueprints, schema definitions, and research documentation. |

---

## 4. 🌿 Git Conventions & Branching Strategy

### Branch Naming Conventions:
- `feat/<scope>-<description>` (e.g., `feat/track-2-citizen-gateway`, `feat/wallet-pwa-qr-scan`)
- `research/<topic>` (e.g., `research/jvm-memory-profiling`, `research/iso-30107-liveness-weights`)
- `fix/<scope>-<description>` (e.g., `fix/keycloak-probe-timeout`, `fix/vdr-context-resolution`)
- `docs/<scope>-<description>` (e.g., `docs/etda-schema-spec`, `docs/runbook-how-to-spin`)
- `chore/<description>` (e.g., `chore/bump-helm-chart-version`, `chore/ci-lint-workflow`)

### Commit Messages (Conventional Commits):
Format: `<type>(<scope>): <short imperative description>`

```bash
feat(identity): add webcam ISO 30107-3 liveness capture to citizen gateway
fix(infra): extend Keycloak startup probe initial delay to 180s for 32GB VM
docs(trust): formalize ETDA StudentID JSON-LD schema specification
research(facepad): publish benchmark results on P1 spoof dataset
```

---

## 5. ✅ Definition of Done (DoD) Quality Gates

Before any PR can be merged, it must satisfy the DoD criteria for its domain:

### For Platform & Infrastructure PRs (`dpi-*`):
- [ ] Automated smoke test verification passes (e.g., `03-verify-smoke-test.sh` reports 10/10 endpoints healthy).
- [ ] Cold boot executes within target latency budgets (< 5 minutes on single VM).
- [ ] Zero credential leaks; `.tfvars` and secrets kept out of git.
- [ ] Clean teardown verified (`terraform destroy` leaves 0 orphaned cloud resources).

### For Biometric & Face-PAD PRs (`facepad-*`):
- [ ] Quantitative benchmark metrics documented (APCER, BPCER, ACER against benchmark datasets).
- [ ] Model inference latency measured under standard browser/edge constraints (< 100ms per frame).
- [ ] Packaged as an immutable Docker image or clean Python module.

### For Application & UI PRs (`app-*`):
- [ ] Responsive UI verified on mobile and desktop viewports.
- [ ] Cryptographic private keys generated and stored strictly client-side (WebCrypto / IndexedDB).
- [ ] Zero hardcoded backend URLs; parameterized via environment variables.
- [ ] Unit and integration test suites pass cleanly.

### For Research & Design PRs (`docs-*`):
- [ ] Written in clear, academic, vendor-neutral English.
- [ ] Mermaid diagrams pass syntax checks without unquoted parenthetical edge breaks.
- [ ] Peer-reviewed and approved by the respective Track Lead or Architect.

---

## 🔒 Security & Secret Management

- **Cloud KMS & Secret Manager:** Production private keys are managed exclusively in Cloud KMS or Kubernetes Secret stores.
- **Reporting Vulnerabilities:** If you discover a security issue or credential exposure, do not open a public issue. Contact the repository maintainers directly or use GitHub Private Vulnerability Reporting.
