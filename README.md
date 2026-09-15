# 🏛️ MOSIP Asia Organization Defaults & Governance (`.github`)

This repository serves as the central administrative and governance hub for the **[mosip-asia](https://github.com/mosip-asia)** organization.

GitHub automatically inherits standard templates, health files, and community standards from this repository across all repositories in the organization.

---

## 📂 Repository Contents

- [**`profile/README.md`**](./profile/README.md): The public organization profile page rendered on GitHub.
- [**`CONTRIBUTING.md`**](./CONTRIBUTING.md): The authoritative MOSIP Asia Engineering Operating Handbook (Branching, PRs, Issue-to-PR flow, DoD).
- [**`LABELS.md`**](./LABELS.md): Standardized color and taxonomy scheme for GitHub labels across all repositories.
- [**`.github/ISSUE_TEMPLATE/`**](./.github/ISSUE_TEMPLATE/):
  - `01_feature_rfc.yml`: Architecture RFCs and feature specifications.
  - `02_research_spike.yml`: Research investigations, ML evaluations, and empirical benchmarks.
  - `03_bug_defect.yml`: Defect reports and deployment troubleshooting.
  - `04_management_milestone.yml`: Grant WBS milestones, contractor deliverables, and audit gates.
  - `config.yml`: Issue form configuration and reference links.
- [**`.github/PULL_REQUEST_TEMPLATE.md`**](./.github/PULL_REQUEST_TEMPLATE.md): Standard pull request template enforcing verification proof, DoD checklists, and issue linking.

---

## 🚀 How This Governs Repositories

Any repository in `mosip-asia` that does not define its own local `.github/ISSUE_TEMPLATE/` or `PULL_REQUEST_TEMPLATE.md` will automatically inherit the templates defined in this repository.

To maintain consistency across all repositories:
1. Always open issues using the structured templates.
2. Link all pull requests with `Closes #XX`.
3. Provide verifiable test proof (smoke test output, benchmark data, or UI screenshots) on every PR.