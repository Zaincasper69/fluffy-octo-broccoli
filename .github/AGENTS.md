# Workspace AI Instructions

This repository is a dev container Feature collection, not a typical application codebase.

## Core structure
- `src/<feature>/devcontainer-feature.json` defines a Feature and its options.
- `src/<feature>/install.sh` is the root-executed entrypoint script for the Feature.
- `src/<feature>/README.md` files are generated documentation for each Feature.
- Add long-form notes for a Feature in `src/<feature>/NOTES.md` instead of directly editing generated README output.
- `test/` contains integration tests and scenario definitions for validating Features.

## What AI agents should do here
- Prefer editing Feature metadata and shell entrypoints instead of inventing new build systems.
- Keep changes aligned with the dev container Feature spec and the repo's existing `examples` pattern.
- Update or add tests under `test/` when changing feature behavior.
- Respect generated documentation: do not manually duplicate full `src/*/README.md` contents.

## Helpful commands
- Run feature tests with the devcontainer CLI, for example:
  - `devcontainer features test --global-scenarios-only`
- The release workflow is defined in `.github/workflows/release.yaml` and uses `devcontainers/action@v1` to publish features and generate documentation.

## Existing custom agent
- This workspace includes a custom agent at `.github/agents/accountings.agent.md` intended for accounting and finance-related guidance.

## Key details
- The repository follows the dev container Feature distribution spec.
- Features are grouped under `src/` and should be versioned and option-driven.
- Use `NOTES.md` for feature-specific author guidance and `README.md` for generated docs.

## When not to use the repo-specific agent
- Do not treat this repository as a generic Node/React project.
- Avoid adding unrelated language-specific tooling unless it directly supports Feature authoring or testing.
