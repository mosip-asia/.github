# 🏛️ Asian Institute of Technology (AIT) — Digital Public Infrastructure (DPI) Center

> **Advancing Sovereign, Disposable, and Standards-Compliant Digital Public Infrastructure for Southeast Asia.**  
> *Supported by the Bill & Melinda Gates Foundation (Ecosystem Grant) in partnership with the MOSIP & Inji Open Source Communities.*

---

## 🌐 Executive Mission

The **AIT Digital Public Infrastructure (DPI) Center** bridges theoretical governance specifications and global digital identity standards with practical, ultra-low-cost, and developer-friendly implementations. 

Our mission is to democratize access to foundational identity, biometric verification, and verifiable credential ecosystems for universities, governments, startups, and developers across Southeast Asia—achieving **99% cost reduction** compared to traditional enterprise deployments through cloud-native automation and open global standards.

---

## 🏛️ The 4 Core R&D Pillars

Our research and engineering initiatives are structured across four autonomous, decoupled pillars:

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                          AIT DPI CENTER — 4 CORE R&D PILLARS                           │
├────────────────────────────┬────────────────────────────┬──────────────────────────────┤
│ 🏗️ PILLAR 1: PLATFORM &    │ 👁️ PILLAR 2: BIOMETRIC    │ 🤖 PILLAR 3: AI ASSISTANT    │
│    DPI SANDBOX             │    R&D & FACE-PAD          │    & AGENTIC SYSTEMS         │
├────────────────────────────┼────────────────────────────┼──────────────────────────────┤
│ • MOSIP Core Identity      │ • ISO/IEC 30107-3 Liveness │ • Conversational Identity    │
│ • Inji Trust Framework     │ • Anti-Spoofing Datasets   │ • Specification RAG Engines  │
│ • <$30/mo Single-VM Boots  │ • Deep Learning Models     │ • Developer Copilots         │
│ • 100% Upstream Parity     │ • $0 Hardware Web Liveness │ • Automated Runbook Agents   │
├────────────────────────────┴────────────────────────────┴──────────────────────────────┤
│ 📱 PILLAR 4: DIGITAL APPLICATIONS & ECOSYSTEM DEVELOPMENT                              │
│ • Sovereign Citizen Web Wallet PWA (Zero App Store gatekeeping)                        │
│ • Hackathon Gateway, Wildcard Team Ingress & OID4VP Submission Portals                 │
│ • Zero-K8s Developer Starter Kits (Python FastAPI, Node.js/TypeScript, Flutter)        │
│ • Commercial & Public Sector Client Integration Projects                               │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

### 1. 🏗️ DPI Platform & Disposable Sandbox (`dpi-*`)
- **Focus:** Automated, disposable cloud-native infrastructure deploying official MOSIP identity microservices and Inji Verifiable Credentials in **<5 minutes** on a single VM at **<$30/month**.
- **Governance:** Implements Thailand's Electronic Transactions Development Agency (**ETDA**) and Digital Government Development Agency (**DGA**) standards, featuring in-cluster Verifiable Data Registries (`did:web`) and `StatusList2021` bitstring revocation.
- **Key Repositories:** [`dpi-sandbox`](https://github.com/mosip-asia/dpi-sandbox) *(Public Sandbox Product)*, [`dpi-base`](https://github.com/mosip-asia/dpi-base) *(Operations Hub)*, [`ait-mosip`](https://github.com/mosip-asia/ait-mosip), [`ait-vc`](https://github.com/mosip-asia/ait-vc).

### 2. 👁️ Biometric R&D & Face-PAD (`facepad-*`)
- **Focus:** Presentation Attack Detection (**PAD**) adhering to **ISO/IEC 30107-3** and biometric quality assessment to **ISO/IEC 19794-5**.
- **Innovation:** Replaces expensive $1,500+ proprietary biometric hardware with camera micro-dynamics and liveness detection runnable directly in modern web browsers.
- **Key Repositories:** [`face-pad`](https://github.com/mosip-asia/face-pad), [`face-pad-model`](https://github.com/mosip-asia/face-pad-model), [`face-pad-datasets`](https://github.com/mosip-asia/face-pad-datasets), [`face-pad-RedTeam`](https://github.com/mosip-asia/face-pad-RedTeam), [`open-pad-platform`](https://github.com/mosip-asia/open-pad-platform).

### 3. 🤖 AI Assistant & Agentic Systems (`ai-*`)
- **Focus:** Autonomous AI agents, developer copilots, and intelligent conversational assistants designed for digital identity platforms.
- **Key Deliverables:** Retrieval-Augmented Generation (RAG) over MOSIP/Inji engineering specifications, intelligent citizen onboarding helpers, and automated infrastructure diagnostic agents.
- **Key Repositories:** [`ai-assistant`](https://github.com/mosip-asia/ai-assistant).

### 4. 📱 Digital Applications & Ecosystem (`app-*`)
- **Focus:** High-performance web and mobile applications enabling citizens and developers to interact with the DPI ecosystem.
- **Key Deliverables:** 
  - **Inji Public Gov Wallet PWA:** Zero-install browser wallet securing private keys in WebCrypto storage.
  - **Hackathon Gateway:** Multi-tenant project submission portal verifying W3C Developer Passports via OpenID for Verifiable Presentations (**OID4VP**).
  - **Developer Toolkits:** Turnkey starter kits in Python, TypeScript, and Flutter.

---

## 🌐 Open Standards & Interoperability

All projects across the AIT DPI Center strictly adhere to global, vendor-neutral specifications:

| Domain | Standard Specifications |
|---|---|
| **Identity & Authentication** | OpenID Connect (OIDC), OAuth 2.0, ISO/IEC 19794-5 Biometric Data Interchange |
| **Presentation Attack Detection** | ISO/IEC 30107-3 (Biometric Presentation Attack Detection - Liveness & Anti-Spoofing) |
| **Verifiable Credentials** | W3C Verifiable Credentials Data Model v2.0, W3C `did:web`, W3C `did:key` |
| **Exchange Protocols** | OpenID for Verifiable Credential Issuance (**OID4VCI**), OpenID for Verifiable Presentations (**OID4VP**) |
| **Trust & Revocation** | W3C `StatusList2021` Bitstring Revocation, ETDA & DGA National JSON-LD Schemas |
| **Cloud & Infrastructure** | CNCF Kubernetes (k3s, RKE2), Helm 3, Terraform, Istio mTLS |

---

## 🛠️ Engineering Framework & Contributing

All repositories in `mosip-asia` operate under a unified engineering governance model:
- **Issue-to-PR Workflow:** Every code change maps to a reviewed GitHub Issue (`Closes #XX`).
- **Docs-as-Code:** Architecture decisions, research spikes, and benchmarks are reviewed via Markdown Pull Requests.
- **Mandatory Verification Gates:** No PR is merged without automated smoke-test passes or benchmark verification.

See our complete [**Organization Contributing & Engineering Handbook**](./CONTRIBUTING.md) for branch naming, PR conventions, and quality gates.

---

## 📬 Contact & Collaboration

- **Academic Host:** Asian Institute of Technology (AIT), Pathum Thani, Thailand
- **Ecosystem:** [MOSIP Open Source Community](https://mosip.io) • [Inji Documentation](https://docs.inji.io)
- **Organization Inquiries:** Contact our leadership via GitHub Discussions or repository issues.
