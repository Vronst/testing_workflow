# Testing Workflow
This repository contains reusable GitHub Actions workflows for consistent automation across multiple projects.
Automatically setups PostgreSQL and runs tests with pytest.

## 🔁 Reusable Testing Workflow

### Usage
```yaml
# Exapmle job
name: test

on:
  push:
    branches:
      - main

# needed permissions
permissions:
  contents: write
  packages: write

# This is most important part
# This uses release workflow
jobs:
  release:
    uses: Vronst/testing_workflow/.github/workflows/testing_workflow.yml@1.0.0
    with:
      container_name: 'container"  # to use with command 'docker exec {name} [...]'
      pytest_flags: ''  # or could be '-m regression' or whatever
```
