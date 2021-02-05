# docker-semantic-release-github-ci
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

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

You have to register a secret token in your repository's settings and called it with `${{ secrets.token_name }}`
