## GitHub Actions workflow that automatically tags a repository when changes are detected in the `module` directory:

---

# Auto Tagging GitHub Workflow

This repository contains a GitHub Actions workflow designed to automatically create and push a version tag whenever changes are detected in the `module` directory upon a push to the `main` branch. This tagging system starts at version `v1.2.1` and increments the patch number until `v1.2.99`, after which it increments the minor version.

## Workflow Details

- **Trigger:** The workflow is triggered on a push to the `main` branch.
- **Change Detection:** It checks for changes specifically within the `module` directory.
- **Versioning:** 
  - It starts at `v1.2.1`.
  - Increases the patch version up to `v1.2.99`.
  - After reaching `v1.2.99`, the minor version increments, resetting the patch version.
- **Tagging:** 
  - A new tag is created and pushed to the repository if changes are detected.
  - Tags are prefixed with `v` (e.g., `v1.2.1`, `v1.2.2`, etc.).

## Prerequisites

- **Permissions:** Ensure that the `GITHUB_TOKEN` has "Read and write permissions". This can be set in the repository settings under "Actions" -> "General" -> "Workflow permissions".
- **Initial Setup:** Ensure that initial tags (such as `v1.2.0` or `v1.2.1`) exist in the repository to maintain continuity.

## Usage

1. **Setup:** Ensure your repository is set up with the default branch as `main` and has the required permissions configured.
2. **Edit and Commit:** Make modifications to the `module` directory.
3. **Push Changes:** Push your changes to the `main` branch.
4. **Auto Tagging:** Upon detecting changes, the workflow automatically increments the version number, creates a new tag, and pushes it to the repository.

## Troubleshooting

If you encounter issues, ensure that:
- The `GITHUB_TOKEN` is properly set up with the required permissions.
- The branch is accurately named `main` in the workflow configuration.
- Organization-wide GitHub Actions settings are not restricting tag creation.

For further assistance, consult the GitHub Actions documentation or review repository settings.

---

This README provides an overview of the functionality, prerequisites, and usage of the auto-tagging workflow, giving users a clear understanding of its purpose and implementation.