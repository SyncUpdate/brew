# Homebrew Release Sync

This repository provides a squashed, linear history of official Homebrew/brew releases.

### Structure
* **`automation` branch (Default):** Contains the GitHub Actions workflow and repository documentation.
* **`main` branch:** Contains the Homebrew source code. Each commit represents one upstream release.

### Workflow
1. The system checks for new tags on the upstream Homebrew repository.
2. When a new tag is found, the file tree of that tag is captured.
3. A single new commit containing that exact file tree is created on the `main` branch.
4. The new commit is parented to the previous release commit on the `main` branch.
5. A local Git tag is created for the new commit, matching the upstream version number (e.g., `4.2.14`).
