# Check License (Local Action)

This local action validates that a required **license key** is available in the workflow and sets it up for later steps.

## Why?

Some private tools, SDKs, or dependencies require a license key before they can be used in CI/CD.  
This action ensures the key is present and exports it as an environment variable for the rest of the job.

---

## Usage

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Check License
        uses: ./.github/actions/check-license
        with:
          license_key: ${{ secrets.LICENSE_KEY }}

      - name: Run Tool
        run: my-licensed-tool --input src/
```

---

## Implementation

This action could be updated to check a license key exists as a secret then activates it, instead of it being provided.
