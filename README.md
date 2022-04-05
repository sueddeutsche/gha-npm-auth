# Github Action NPM auth

Setup npm authentication

## Usage

Store the npm token as a secret `NPM_TOKEN` in the repositories secrets. `Settings > Secrets > Actions`.

Use it in a workflow like this:

```yaml
name: My workflow
on:
  push:

jobs:
  test:
    name: Test
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: sueddeutsche/gha-npm-auth@v2
        with:
          npm-token: ${{ secrets.NPM_TOKEN }}
```
