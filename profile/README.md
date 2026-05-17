# release.tools

Small, focused tools for cutting releases and keeping CI from stepping on itself.

## What's here

- **[cli](https://github.com/releasetools/cli)** — Shell helpers for the boring parts of releasing (version bumps, tag pushes, etc.). Use it as a composite action with `uses: releasetools/cli@<version>`, or install locally via the [Homebrew tap](https://github.com/releasetools/homebrew-tap).
- **[actions](https://github.com/releasetools/actions)** — Reusable GitHub Actions. Currently: `signed-push`, which commits to a branch via GitHub's `createCommitOnBranch` GraphQL mutation, so commits are signed server-side without a GPG key on the runner.
- **[mutex](https://github.com/releasetools/mutex)** — Postgres-backed advisory lock for CI workflows. Tells one job to wait while another finishes; pings Slack if a holder vanishes mid-run.
- **[homebrew-tap](https://github.com/releasetools/homebrew-tap)** — `brew tap releasetools/tap && brew install releasetools-cli`.

## License

Apache-2.0 unless a repo says otherwise.

---

Maintained by [@MihaiBojin](https://github.com/MihaiBojin). Issues and PRs welcome on each repo.
