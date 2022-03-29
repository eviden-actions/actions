# Actions

Reusable actions for the ATOS-Actions organization.

[![Release](https://github.com/ATOS-Actions/actions/actions/workflows/on_push.yml/badge.svg)](https://github.com/ATOS-Actions/actions/actions/workflows/on_push.yml)

## Usage

```
steps:
- uses: ATOS-Actions/actions/.github/workflows/release@v1
	secrets:
  	GH_TOKEN: ${{ secrets.GH_TOKEN  }}
```

## Actions

| Action       | Description                                   | Args |
| ------------ | --------------------------------------------- | :--: |
| `dependabot` | Automatically merge and approve dependabot PR | Yes  |
| `lint-code`  | Check code style and coding guidelines        |  No  |
| `lint-pr`    | Check PR is matching contributing guidelines  |  No  |
| `release`    | Release a new version with semantical release | Yes  |

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
