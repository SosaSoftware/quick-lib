# Contributing to Quick Lib

Thank you for your interest in contributing to Quick Lib.

This project follows a structured workflow to maintain deterministic versioning, a clean history, and controlled releases. The goal is to keep the library reliable, predictable, and production-ready while remaining open to meaningful improvements.

---

## Branching Model

All contributions must originate from branches created from `main`.

Branch names must follow one of the approved prefixes. Pull Requests created from non-compliant branch names will fail validation and cannot be merged.

Approved branch naming patterns:

- `feature/<short-description>`
- `fix/<short-description>`
- `refactor/<short-description>`
- `chore/<short-description>`
- `docs/<short-description>`
- `test/<short-description>`
- `perf/<short-description>`

Branch names must use lowercase characters and may only include letters, numbers, dots (`.`), underscores (`_`), and hyphens (`-`) in the description segment.

Pull Requests must target `main`.

Direct commits to `main` are not permitted.

---

## Pull Request Standards

### Conventional Commits (Mandatory)

Pull Request titles must comply with the Conventional Commits specification.

Format:

```
<type>: <description>
```

Recognized types and their semantic impact:

- `fix:` → PATCH version increment
- `feat:` → MINOR version increment
- `feat!:` → MAJOR version increment
- `refactor:` → no version increment unless `!` is used
- `chore:` → no version increment unless `!` is used

Pull Requests that do not comply with this format will fail validation and cannot be merged.

This requirement ensures consistent automated version management and predictable releases.

---

## Merge Strategy

The `main` branch uses squash merges exclusively.

The resulting squash commit message serves as the single source of truth for automated semantic version calculation.

This guarantees:

- A clean and linear project history
- Deterministic semantic versioning
- One logical change per merge

---

## Automated Version Management

After each successful merge into `main`:

- `package.json.version` is updated automatically according to the squash commit message.
- Versioning strictly follows Semantic Versioning (SemVer):
  - PATCH → bug fixes
  - MINOR → backward-compatible features
  - MAJOR → breaking changes

Manual version changes are not part of the contribution workflow.

---

## Automatic Tag Policy

When a change produces a MAJOR version increment:

- A Git tag `vX.Y.Z` is generated automatically by repository automation.

Tags matching the `v*` pattern are protected and may only be created or modified by authorized maintainers.

---

## Release Governance

Release creation and package publication are restricted to the project owner.

Contributors are not responsible for release management or publishing operations.

---

## Contribution Ownership

By submitting a Pull Request, you agree that your contribution becomes part of the Quick Lib codebase and may be used, modified, and distributed as part of the project.

All accepted contributions are considered a voluntary contribution to the project without expectation of compensation.

---

## Local Validation

Contributors are expected to ensure that changes build successfully and, where applicable, pass existing tests before opening a Pull Request.

---

## Repository Protection

- The `main` branch is protected.
- Conventional Commit validation is enforced.
- Required status checks must pass before merging.
- Changes to workflow definitions under `.github/workflows/**` require approval from designated code owners.

---

We appreciate thoughtful contributions that improve clarity, consistency, and long-term maintainability.
