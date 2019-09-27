## Usage
```
name: Semantic Release

on: pull_request

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - uses: autoricardo/actions/phraseapp-sort
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
