# 🏛️ Organization-Wide AI Agent Guidelines — MOSIP Asia

> **Canonical System Instructions for AI Agents & Pair Programmers**  
> This file is the authoritative single source of truth for **all** AI assistants (Google Antigravity, Anthropic Claude Code, ChatGPT / OpenAI, GitHub Copilot, Cursor, Windsurf, Aider) operating across the entire `mosip-asia` organization.  
> *Cross-tool mirrors:* Automatically recognized via `CLAUDE.md`, `.cursorrules`, `.windsurfrules`, and `.github/copilot-instructions.md`.

---

## 1. 🌐 Organization Scope & The 4 Core R&D Pillars

The **Asian Institute of Technology (AIT) DPI Center** operates four autonomous, decoupled engineering pillars:

| Pillar | Focus Area | Scope & Key Repositories | Core Standards & Technologies |
|---|---|---|---|
| **🏗️ Pillar 1: DPI Platform & Sandbox** (`dpi-*`) | Cloud Infra, MOSIP Core Identity, and Trust Framework | [`sandbox`](https://github.com/mosip-asia/sandbox), [`ait-mosip`](https://github.com/mosip-asia/ait-mosip), [`ait-vc`](https://github.com/mosip-asia/ait-vc), [`dpi-base`](https://github.com/mosip-asia/dpi-base) | CNCF Kubernetes (k3s, RKE2), Helm 3, Terraform, S3 State, Istio mTLS, Keycloak OIDC, W3C `did:web`, `StatusList2021` |
| **👁️ Pillar 2: Biometric R&D & Face-PAD** (`facepad-*`) | Liveness Detection & Biometric Verification | [`face-pad`](https://github.com/mosip-asia/face-pad), [`face-pad-model`](https://github.com/mosip-asia/face-pad-model), [`face-pad-datasets`](https://github.com/mosip-asia/face-pad-datasets), [`face-pad-RedTeam`](https://github.com/mosip-asia/face-pad-RedTeam) | ISO/IEC 30107-3 (Presentation Attack Detection / PAD), ISO/IEC 19794-5 (Biometric Quality), PyTorch, ONNX, Web Liveness |
| **🤖 Pillar 3: AI Assistant & Agents** (`ai-*`) | Identity Copilots & Agentic Systems | [`ai-assistant`](https://github.com/mosip-asia/ai-assistant) | LangChain, LlamaIndex, Multi-Agent Systems, RAG over DPI Specs, Automated Diagnostic Agents |
| **📱 Pillar 4: Applications & Ecosystem** (`app-*`) | Citizen Wallets, Developer Portals, and Client Apps | [`app-wallet-pwa`](https://github.com/mosip-asia/ait-vc), [`vc-hackathon`](https://github.com/mosip-asia/sandbox), New Client Solutions | Progressive Web Apps (PWA), WebCrypto API, OID4VCI, OID4VP, TypeScript/React, Python FastAPI, Flutter |

---

## 2. 🏛️ The 3-Tier Repository Architecture

To prevent clutter, maintain strict confidentiality, and scale across multiple projects, repositories are strictly partitioned into 3 tiers:

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        THE 3-TIER REPOSITORY SEPARATION                                │
├────────────────────────────────────────────────────────────────────────────────────────┤
│                                                                                        │
│  1. 🔒 PRIVATE MANAGEMENT REPO (mosip-asia/management)                                │
│     • Audience: Project Director & Core Leadership ONLY.                              │
│     • Contents: Grant contracts (Gates Foundation), consultant ToRs, budgets, hiring.  │
│     • Home of: Tier-1 Portfolio Management Board. NEVER submoduled into dev code.      │
│                                                                                        │
│  2. 📘 SHARED/PUBLIC TECH SPECS (mosip-asia/docs-*)                                   │
│     • Audience: All architects, researchers, and engineers.                           │
│     • Contents: Master system specs, RFCs, JSON-LD schemas, and research benchmarks.   │
│     • Attached as: Git submodules at `./docs` inside development code repositories.    │
│                                                                                        │
│  3. 💻 DEVELOPMENT REPOSITORIES (mosip-asia/dpi-*, facepad-*, ai-*, app-*)            │
│     • Audience: Domain development teams.                                             │
│     • Contents: Source code, Dockerfiles, unit tests, and Helm charts.                 │
│                                                                                        │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. 🔄 Universal Engineering Operating Rules for AI Agents

Whenever assisting with code, architecture, or repository management, AI agents MUST follow these principles:

### 1. The Issue-to-PR Contract
- **Never perform untracked work:** Every code modification must link to an existing or newly drafted GitHub Issue (`Closes #XX`).
- **Issue Types:**
  - `type:rfc` for technical architecture designs or schema additions.
  - `type:research` for ML evaluations, time-boxed spikes, or empirical benchmarks.
  - `type:feature` for implementation tasks.
  - `type:bug` for defects, pod timeouts, or pipeline failures.
  - `type:milestone` for grant deliverables and release gates.
- **Pull Request Quality Gate:** Every PR must include verifiable test proof (smoke test output for platform, APCER/BPCER accuracy for ML, UI screenshots for frontend).

### 2. Pure Upstream Helm Parity (Platform Guardrail)
- **Never modify official MOSIP or Inji Docker images or chart templates:** Upstream microservices are headless consumers.
- Configure all parameters strictly through declarative Helm values, ConfigMaps, and Terraform `.tfvars`.

### 3. Decoupled Black-Box Contracts
- Pillar 2 (Face-PAD) delivers an immutable Docker image or API (`POST /verify-face-liveness`); it does NOT manage cloud infrastructure.
- Pillar 3 (AI Assistant) delivers an API endpoint or embeddable chat widget.
- Pillar 1 (Platform) provides the Kubernetes substrate, Keycloak OIDC authentication, and ingress routing.
- Pillar 4 (Apps) consumes these services via standard REST/OIDC protocols.

### 4. Docs-as-Code & Information Architecture
- System architecture decisions (ADRs), schemas, and research reports must be written in clear Markdown and reviewed via Pull Requests.
- **Tier 1 Specs:** Centralized in `docs-*` repositories.
- **Component Runbooks:** Stored in the local repository root (`README.md`, `runbooks/`).
- **Archive & Historical Papers:** Stored in `archive/` or `literature_review/`.

### 5. Security & Secret Hygiene
- **STOP & VERIFY:** Never commit `.env`, `.tfvars`, private keys, or API tokens.
- Keep credentials untracked via `.gitignore`.
- Production private keys must be anchored in Cloud KMS or Kubernetes Secret stores.

### 6. Mermaid Diagram Formatting Guardrail
- Always enclose edge labels with parentheses `(...)`, formatting breaks (`<br/>`), or slashes in double quotes: `-->|"OID4VCI Protocol (Issues VC)"|`.
- Unquoted parentheses in pipe delimiters `|...|` cause Mermaid's lexer to emit a fatal `PS` parse error.

---

## 4. 🏷️ Standard Repository Naming Convention

When creating or recommending new repositories, AI agents must enforce the standard prefix:
- `dpi-<component>`: Platform, infrastructure, or sandbox components.
- `facepad-<component>`: Biometrics, presentation attack detection, datasets, or models.
- `ai-<component>`: Conversational assistants, agents, or LLM pipelines.
- `app-<component>`: Frontends, citizen wallets, portals, or client projects.
- `docs-<component>`: Centralized specifications and research documentation.
- `management`: Private leadership, grant tracking, and contract administration.

---

## 5. 👥 Key Grant Milestone Context (Gates Foundation Outcome 0)

For Platform & Sandbox tasks, keep in mind the active delivery milestones:
- **Milestone 1.5.1 Baseline (Target: 30 Sep 2026):** Vanilla MOSIP RDI baseline and Inji container baseline verified on target cloud compute.
- **Milestone 1.5.2 Lifecycle (Target: 31 Oct 2026):** IaC transition complete, single-VM `PROFILE=hackathon` (<5m boot, <$30/mo), Nightly TTL Cost Reaper, Layer-1 VCGA/VDR.
- **Milestone 1.5.3 Hardening (Target: 31 Dec 2026):** 100% Code Freeze, Inji Certify/Verify, Web Wallet PWA, 10-team simulated dry run.
- **Milestone 1.5.4 Operational Setup at AIT (Target: 30 Jan 2027):** 3-minute smoke test verification, official Deliverable 1 Technical Report to Gates Foundation.
