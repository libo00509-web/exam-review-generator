# Repository Guidelines

## Project Structure & Module Organization

This repository is currently an empty Git repository for `exam-review-generator`. No application code, tests, assets, or dependency manifests exist yet. When adding the initial implementation, keep application code in `src/`, automated tests in `tests/`, and static resources in `assets/` where appropriate. Document the actual layout in this guide as the project develops.

## Build, Test, and Development Commands

No build, test, or local development commands are configured. Do not assume commands such as `npm test` or `make build` are available. When selecting the project toolchain, add reproducible setup, development, build, and test commands to a root `README.md`. Commit the dependency manifest and its corresponding lockfile, and keep this section synchronized with the supported commands.

## Coding Style & Naming Conventions

No language, formatter, or linter has been selected. Follow the conventions of the chosen language and configure formatting and linting early. Use descriptive names that reflect responsibility, keep modules focused, and avoid unrelated formatting changes. Apply one consistent indentation style per language through the formatter configuration.

## Testing Guidelines

No testing framework or coverage threshold is configured. Introduce automated tests alongside new behavior, including representative inputs, boundary cases, and failure paths. Use descriptive test names that explain the expected outcome. Document test discovery patterns and execution commands when the framework is added.

## Commit & Pull Request Guidelines

There is no commit history from which to infer a message convention. Use concise, imperative commit subjects, such as `Add review generation workflow`, and keep commits focused. Pull requests should describe the problem, the change, and validation performed. Link relevant issues and include screenshots for visible interface changes. Explicitly state when validation could not be run and why.

## Security & Configuration

Keep credentials, private exam materials, and personal data out of version control. Provide placeholder configuration examples and ignore local secrets and generated artifacts as the implementation takes shape.
