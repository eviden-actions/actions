# Actions

Reusable actions for the eviden-actions organization.

[![Release](https://github.com/eviden-actions/actions/actions/workflows/release.yml/badge.svg)](https://github.com/eviden-actions/actions/actions/workflows/release.yml)

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
      RELEASE_APP_ID: ${{ secrets.RELEASE_APP_ID }}
      RELEASE_APP_PRIVATE_KEY: ${{ secrets.RELEASE_APP_PRIVATE_KEY }}
```

## Actions

| Action      | Description                                   | Args |
| ----------- | --------------------------------------------- | :--: |
| `lint-code` | Check code style and coding guidelines        |  No  |
| `lint-pr`   | Check PR is matching contributing guidelines  |  No  |
| `release`   | Release a new version with semantical release | Yes  |

### Release

Arguments for the `release` action:

| Secrets                   | Description                             | Required |
| ------------------------- | --------------------------------------- | :------: |
| `RELEASE_APP_ID`          | The App ID of the Atos Release App      |   Yes    |
| `RELEASE_APP_PRIVATE_KEY` | The private key of the Atos Release App |   Yes    |
