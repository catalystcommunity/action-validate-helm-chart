<!-- start title -->

# GitHub Action:Validate Helm Chart

<!-- end title -->
<!-- start description -->

Validates a helm chart using helm lint, and helm template commands. Optionally validates that the only branch merged into main is alpha

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: catalystsquad/action-validate-helm-chart@undefined
  with:
    # When true, the action will fail if the pull request is into the `main` branch
    # and the source branch is not `alpha`
    # Default: true
    validate-main-alpha-merge: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**                       | **Description**                                                                                                    | **Default** | **Required** |
| :------------------------------ | :----------------------------------------------------------------------------------------------------------------- | :---------: | :----------: |
| **`validate-main-alpha-merge`** | When true, the action will fail if the pull request is into the `main` branch and the source branch is not `alpha` |   `true`    |  **false**   |

<!-- end inputs -->
<!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
<!-- start examples -->

### Example usage

```yaml
name: Validate Helm Chart PR
on:
  pull_request:
    branches:
      - main
      - alpha
    paths:
      - "chart/**"
jobs:
  validate-chart:
    if: ${{ !startsWith( github.head_ref, 'automated-code-release' ) }}
    name: Lint Chart
    runs-on: ubuntu-latest
    steps:
      - uses: crazy-max/ghaction-dump-context@v1
      - uses: catalystsquad/action-validate-helm-chart@v1
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
