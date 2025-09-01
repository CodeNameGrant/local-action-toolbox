# Local Action Toolbox

Contains examples of **local GitHub Actions** explained byt Dev.to post [Supercharging Your Workflows with Local GitHub Actions](https://dev.to/codenamegrant/supercharging-your-workflows-with-local-github-actions-2o23)

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
