# Woodpecker
This action provides visualization of various metrics about the pull request.

Currently, only *pull_request_review* triggers are supported, and they are only triggered when approved.

### Reference
- [5 metrics Engineering Managers can extract from Pull Requests](https://sourcelevel.io/blog/5-metrics-engineering-managers-can-extract-from-pull-requests)

## Example
![スクリーンショット 2023-02-12 21 16 03](https://user-images.githubusercontent.com/20347995/218310501-1a39fe33-9385-47b7-9cb0-a8e16d17e31a.png)

## Example usage

```yaml
name: comment pr metrics
on:
  pull_request_review:
    branches:
      - develop
    types: [submitted]
jobs:
  woodpecker:
    runs-on: ubuntu-latest
    env:
      GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: comment pr metrics
        uses: r-kagaya/woodpecker
```