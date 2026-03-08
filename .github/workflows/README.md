# GitHub Workflows

This repository uses GitHub Actions to automate validation, building, versioning, and publishing.  
Each workflow has a single responsibility within the release pipeline.

---

## Pull Request Validation

**Workflow file**

`.github/workflows/validation.yml`

**Purpose**

Ensures that every Pull Request follows the repository conventions before it can be merged.

This workflow validates:

- Pull Request title follows **Conventional Commits**
- Pull Request template is filled correctly
- Required checklist items are completed

This guarantees that commits entering `main` have a consistent format and can be used by the version automation process.

**Trigger**

`pull_request`

Runs when a PR is opened, synchronized, or reopened.

---

## Build

**Workflow file**

`.github/workflows/build.yml`

**Purpose**

Confirms that the project builds successfully before changes are merged.

Steps performed:

- Install dependencies
- Compile the TypeScript project
- Run tests (if configured)

This ensures the repository remains in a working state after every merge.

**Trigger**

`pull_request`

Runs automatically for every Pull Request.

---

## Version Automation

**Workflow file**

`.github/workflows/version.yml`

**Purpose**

Automatically updates the library version after a Pull Request is merged into `main`.

The version bump is determined from the commit message created during the squash merge.

**Version rules**

- `feat:` → minor version bump
- `fix:` → patch version bump
- `type!:` → major version bump

Example:

`feat: add new API gateway construct`

Results in:

`1.2.0 → 1.3.0`

The workflow performs the following actions:

- Reads the latest commit message on `main`
- Determines the required semantic version bump
- Updates `package.json`
- Creates an automated commit with the new version

**Trigger**

`push → main`

Runs automatically after Pull Requests are merged.

---

## Release

**Workflow file**

`.github/workflows/release.yml`

**Purpose**

Publishes the package when a GitHub Release is created.

The workflow:

- Installs dependencies
- Builds the project
- Publishes the package to GitHub Packages

Publishing is intentionally **manual** to ensure maintainers control when a version becomes publicly available.

**Trigger**

`release.published`

The workflow runs when a new GitHub Release is published.
