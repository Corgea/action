# Corgea Github Action
This action will scan your code for vulnerabilties and Corgea will comment on the PR for with fixes.

## Inputs
### `corgea-token`
**Required** Your Corgea token from https://www.corgea.app/integrations/ 


## Example
```
name: Corgea Scan

on: 
  pull_request:
    types:
      - opened

jobs:
  scan:
    name: scan
    runs-on: ubuntu-latest
    if: (github.actor != 'dependabot[bot]')

    steps:
      - uses: actions/checkout@v4
      - uses: corgea/action@v1
        with:
          corgea-token: ${{ secrets.CORGEA_TOKEN }}
```
