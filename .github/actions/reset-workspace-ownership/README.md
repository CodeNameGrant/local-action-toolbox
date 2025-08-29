# Reset Workspace Ownership (Local Action)

This local composite action ensures that all files in the GitHub Actions workspace are reset to the **current user’s ownership** using [peter-murray/reset-workspace-ownership-action](https://github.com/peter-murray/reset-workspace-ownership-action), with the `user_id` automatically detected.

## Why?

When running GitHub Actions on **self-hosted runners with containers**, files created inside the GITHUB_WORKSPACE may end up owned by root (or another container user). Since the runner itself usually doesn’t run as root, this can cause later steps—like `actions/checkout` to fail when trying to clean or modify the workspace.

Resetting workspace ownership ensures all files are owned by the same user as the runner, preventing permission errors across workflow runs.

---

## Usage

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Reset Workspace Ownership
        uses: ./.github/actions/reset-workspace-ownership
```

### Inputs

None. The action automatically determines the uid.

### Outputs

None.
