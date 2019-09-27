## Usage
```
name: Semantic Release

on: pull_request

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@master
        with:
          fetch-depth: 1

      - name: sort
        uses: autoricardo/github-actions/phraseapp-sort
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - name: push
        uses: github-actions-x/commit@v2.1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          push-branch: ${{ GITHUB_REF }}
          commit-message: "Sort translations"
          force-add: "true"
```
