# Shared no-mistakes gate end-to-end evidence

Executed the exact `verify.py` fetched from the workflow's immutable action pin `32d396ac0f29135daf7fcb9964aba9d5f4e796d6`, using GitHub-style `pull_request` event payloads.

### Compliant body bound to current head

Exit code: `0`

```text
Found no-mistakes signature in PR #42 body.
Found structurally compliant pipeline step attestation.
::warning::PR-body attestation is author-editable and is not cryptographic proof that no-mistakes produced it.
```

### Stale body after a direct push

Exit code: `1`

```text
Found no-mistakes signature in PR #42 body.
::error::Pipeline attestation head_sha does not match the current PR head.

attestation.head_sha: 0000000000000000000000000000000000000000
PR head: a4a9b8347b70a535345a66490aacacf070c8c701

A later push must not pass on an older attestation. Re-run 'git push no-mistakes' so the PR body attestation binds to the current head.

See CONTRIBUTING.md for setup and the full workflow.

PR author: contributor
```

### Intended last-wins duplicate verdict

Exit code: `0`

```text
Found no-mistakes signature in PR #42 body.
Found structurally compliant pipeline step attestation.
::warning::PR-body attestation is author-editable and is not cryptographic proof that no-mistakes produced it.
```

## Parsed GitHub workflow contract

The `yaml` package normalized the machine-consumed workflow.

- pull_request dispatch types: opened, edited, reopened
- synchronize dispatches gate: false
- caller step: kunchenguid/no-mistakes/.github/actions/require-no-mistakes@32d396ac0f29135daf7fcb9964aba9d5f4e796d6
- local run step exists: false
- release outputs ignored: .release-please-manifest.json, CHANGELOG.md, package.json
- preserved from base:
  - target_branches: preserved
  - paths_ignore: preserved
  - permissions: preserved
  - concurrency: preserved
  - job_name: preserved
  - author_exemption_expression: preserved
  - runner: preserved
