# Local Action Toolbox

This repository contains examples of **local GitHub Actions**.  
Local actions live inside a repository (usually in `.github/actions/`) and are meant to solve **project- or org-specific workflow needs** without being published to the GitHub Marketplace.

They’re great for:

- Wrapping third-party actions with custom defaults
- Enforcing org-specific conventions
- Running checks or setup steps unique to your project

---

## Examples

- [**Bootstrap Node**](.github/actions/bootstrap-node)  
  Sets up Node.js with project-specific defaults (versions, caching, dependencies).

- [**Check License**](.github/actions/check-license)  
  Ensures a required license key is available and activates it for subsequent steps.

- [**Reset Workspace Ownership**](.github/actions/reset-workspace-ownership)  
  Resets file and directory ownership inside the `GITHUB_WORKSPACE` to prevent permission issues when using containers on self-hosted runners.

---

## Usage

To use any local action in a workflow, reference it by its relative path:

```yaml
jobs:
  example:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run local action
        uses: ./.github/actions/check-license
        with:
          license_key: ${{ secrets.LICENSE_KEY }}
```
