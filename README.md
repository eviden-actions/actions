# Actions

Reusable actions for the eviden-actions organization.

[![Release](https://github.com/eviden-actions/actions/actions/workflows/on_push.yml/badge.svg)](https://github.com/eviden-actions/actions/actions/workflows/on_push.yml)

## Usage

```
on:
  push:

jobs:
  validate:
    uses: eviden-actions/actions/.github/workflows/lint-code.yml@v1

  release:
    needs: [validate]
    uses: eviden-actions/actions/.github/workflows/release.yml@v1
    secrets:
      GH_TOKEN: ${{ secrets.GH_TOKEN  }}
```

## Actions

| Action            | Description                                     | Args |
| ----------------- | ----------------------------------------------- | :--: |
| `cancel-workflow` | Cancels previous instances of the same workflow |  No  |
| `dependabot`      | Automatically merge and approve dependabot PR   | Yes  |
| `lint-code`       | Check code style and coding guidelines          |  No  |
| `lint-pr`         | Check PR is matching contributing guidelines    |  No  |
| `release`         | Release a new version with semantical release   | Yes  |

### Dependabot

Arguments for the `dependabot` action:

| Secrets    | Description                               | Required |
| ---------- | ----------------------------------------- | :------: |
| `GH_TOKEN` | Add a code owner PT on protected branches |    No    |

### Release

Arguments for the `release` action:

| Secrets    | Description                               | Required |
| ---------- | ----------------------------------------- | :------: |
| `GH_TOKEN` | Add a code owner PT on protected branches |    No    |
