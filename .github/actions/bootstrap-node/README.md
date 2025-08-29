# Bootstrap Node Environment

Sets up Node.js and optionally installs npm dependencies for your project.

---

## Usage

```yaml
jobs:
  setup:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0

      - name: Bootstrap Node Environment
        uses: ./.github/actions/bootstrap-node
        with:
          installDeps: 'true' # optional, default is 'true'
```

## Inputs

Input Required Default Description

- `installDeps` Whether to run npm ci to install dependencies. Default: true

## Outputs

This action does not produce any outputs.

## Notes

- Sets up Node using [actions/setup-node@v4](https://github.com/actions/setup-node).
- Uses Node.js version 20.
- Caches npm dependencies automatically.
- If installDeps is set to 'false', only Node.js will be set up.
