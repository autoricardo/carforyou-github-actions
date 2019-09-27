## Usage
```
name: Phraseapp sort

on:
  pull_request:
    paths:
      - static/locales/**/*

jobs:
  sort:
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@master

      - name: sort
        id: sort
        uses: autoricardo/carforyou-github-actions/phraseapp-sort@master
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - name: push
        uses: github-actions-x/commit@v2.1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          push-branch: ${{ github.head_ref }}
          commit-message: "Sort translations"
          force-add: "true"
```
