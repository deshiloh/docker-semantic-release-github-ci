# docker-semantic-release-github-ci

## Basic usage : 

```
name: Release
on:
  push:
    branches:
      - master
jobs:
  release:
    name: Release
    runs-on: ubuntu-18.04
    steps:
      - name: Checkout
        uses: actions/checkout@v1
      - name: Setup Semantic
        uses: docker://deshiloh/docker-semantic-release-github-ci
      - name: Release
        env:
          GITHUB_TOKEN: ${{ secrets.TOKEN }}
        run: npx semantic-release
```
