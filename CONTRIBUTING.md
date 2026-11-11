# Contributing to g-udi

Thanks for taking the time to improve a g-udi project. This guide applies to the public repositories in the organization unless a repository has a more specific contributing document.

## Before You Start

- Use an issue for bugs, design questions, larger refactors, new public behavior, or cross-repo changes.
- Small documentation fixes, typo fixes, and narrow bug fixes can go straight to a pull request.
- Check the repository README for setup, configuration, and validation commands.
- Keep private templates, machine-local paths, credentials, and generated runtime output out of commits.

## Working Locally

1. Fork or clone the target repository.
2. Create a focused branch.
3. Make the smallest change that solves the issue cleanly.
4. Run the repository's smoke test or validation command (see below for the repositories that have none).
5. Update README or plugin docs when user-facing behavior changes.

Common validation commands used across the repos include:

```sh
test/run
./test/smoke.sh
./test/test.sh
git diff --check
shellcheck -x path/to/script.sh
```

Use the command documented by the repository you are changing.

The Bash component repositories ([gaudi-bash-aliases](https://github.com/g-udi/gaudi-bash-aliases), [gaudi-bash-completions](https://github.com/g-udi/gaudi-bash-completions) and [gaudi-bash-plugins](https://github.com/g-udi/gaudi-bash-plugins)) do not ship a smoke test. For those, check every file you changed for syntax and lint errors instead:

```sh
bash -n path/to/changed-file.bash
shellcheck -s bash path/to/changed-file.bash
```

## Shell Code Standards

Most g-udi projects are shell-heavy. Please follow these rules:

- Prefer Bash when the repository is already Bash-based.
- Use `#!/usr/bin/env bash` for executable Bash scripts.
- Quote variable expansions unless word splitting is explicitly intended.
- Prefer arrays over string-built commands.
- Use `command -v` or local helper functions for dependency detection.
- Keep installers idempotent; running setup twice should not duplicate profile lines or corrupt state.
- Do not hide failures silently unless the feature is explicitly optional.

## JavaScript and Widget Standards

For Übersicht and desktop widget repositories:

- Keep widget refresh intervals proportional to the data source.
- Avoid overlapping async work for the same widget.
- Handle missing credentials, missing local apps, and unavailable command-line tools without crashing the whole widget.
- Keep user configuration in documented files or environment variables.
- Do not commit local secrets, app caches, or generated data files.

## Documentation Standards

READMEs should include:

- What the project does.
- Who it is for.
- Installation steps.
- Configuration details.
- Available commands, plugins, widgets, or segments.
- Validation or test instructions.
- Notes about optional dependencies.

If a README has screenshots or visual examples, preserve them unless they are inaccurate.

## Pull Request Checklist

Before opening a pull request:

- The branch is focused and does not include unrelated formatting churn.
- The relevant smoke test passes or, for the Bash component repositories without one, `bash -n` and `shellcheck` are clean on every changed file.
- `git diff --check` is clean.
- Documentation is updated for user-facing changes.
- Secrets, private paths, generated output, and local caches are not committed.
- The PR description explains what changed and how it was validated.

## Cross-Repo Changes

Some g-udi projects are intentionally related, especially the shell framework and Bash component repositories. For cross-repo work:

- Mention all affected repositories in the issue or PR description.
- Land dependency changes first when possible.
- Keep compatibility notes in the README or changelog when behavior changes.
- Avoid making a repo depend on private templates or local-only paths.

## Security

Do not report secrets, tokens, or sensitive local-machine details in public issues. If you discover exposed credentials in a repository, rotate the credential first and then open a minimal issue or pull request that removes the secret and documents the safer configuration path.
