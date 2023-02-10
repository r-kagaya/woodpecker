# Woodpecker
This action provides visualization of various metrics about the pull request
Currently, only pull_request_review triggers are supported, and they are only triggered when approved.

## Example usage

```yaml
name: comment pr metrics
on:
  pull_request_review:
    branches:
      - develop
    types: [submitted]
jobs:
  lead-time:
    runs-on: ubuntu-latest
    env:
      GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: comment pr metrics
        uses: actions/woodpecker
```