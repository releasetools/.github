# release.tools

Tools and conventions for releasing software, with checks in pull requests and automation for publishing.

## What's here

| Repository | What it does |
| --- | --- |
| [conventions](https://github.com/releasetools/conventions) | Individually adoptable practices for versioning and release notes, with conventions for documentation and agent indexes. Defines the shared `.releasetools.yaml` format and provides guides for running repositories. |
| [cli](https://github.com/releasetools/cli) | Shell commands, available as `releasetools` and `rt`, for release prechecks, version bumps, signed tags, and release bookkeeping. Checks branch membership and registry availability, extracts changelog sections, and waits for workflows or published URLs. Available locally and as a GitHub Action. |
| [actions](https://github.com/releasetools/actions) | Four GitHub Actions: `signed-push` publishes files with a GitHub-signed commit and optional tags; `versions-guard` checks version bumps against change types; `changelog-guard` checks changelog entries; `extract-release-notes` reads a version's changelog section for publishing. Also publishes `@releasetools/config`. |
| [agent-plugins](https://github.com/releasetools/agent-plugins) | The `release-tools` marketplace for Claude Code and Codex, with installation support for Hermes and Antigravity. `release-notes` writes individual changes' notes and prepares release entries. `release` runs the configured release workflow through checks, a pull request, merge, and publishing. `mutex` lets agents hold locks around shared work. |
| [mutex](https://github.com/releasetools/mutex) | PostgreSQL-backed locks shared by a GitHub Action and the `@releasetools/mutex` CLI. Wraps programs with automatically renewed locks, releases workflow locks when jobs finish, and reports activity on pull requests and optionally Slack. Supports connection profiles and a server with pooled database connections. |
| [homebrew-tap](https://github.com/releasetools/homebrew-tap) | Homebrew distribution of `releasetools-cli`, providing both `releasetools` and `rt`. The formula follows CLI releases. |
| [terraform-modules](https://github.com/releasetools/terraform-modules) | Terraform modules for configuring GitHub repositories and managing a shared GitHub App. `github-repo` covers repository settings and branch rules; `github-app` covers App creation, credentials, and installation access. |
| [.github](https://github.com/releasetools/.github) | Organization defaults for contributing and support, security reporting, a code of conduct, and issue and pull request templates. |

## Using the tools together

[`.releasetools.yaml`](https://github.com/releasetools/conventions/blob/main/FORMAT.md) declares project paths,
version manifests, changelog locations, and release commands. The Actions and agent plugins read those declarations
to check and release the named projects. Conventions can be adopted individually, and each convention names any
tool that checks it.

The [`@releasetools/config` adoption command](https://github.com/releasetools/actions/tree/main/packages/config#adopt-the-conventions)
writes a starter configuration from a repository's manifests and changelog, and prints plugin installation commands.
The [guides](https://github.com/releasetools/conventions/tree/main/guides) cover release notes and repository practices.

## Contributing and support

See the [contribution guidelines](https://github.com/releasetools/.github/blob/main/CONTRIBUTING.md) and each
repository's build and release instructions. Questions belong in that repository's Discussions or issues, as
described in [Support](https://github.com/releasetools/.github/blob/main/SUPPORT.md). Report vulnerabilities through
[private security reporting](https://github.com/releasetools/.github/blob/main/SECURITY.md).

## License

Apache-2.0 unless a repo says otherwise.

---

Maintained by [@MihaiBojin](https://github.com/MihaiBojin).
