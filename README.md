<!-- start title -->

# GitHub Action:Hello World

<!-- end title -->
<!-- start description -->

Greet someone

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: catalystsquad/action-composite-action-template@undefined
  with:
    # Who to greet
    # Default: World
    who-to-greet: ""
```

<!-- end usage -->
<!-- start inputs -->

| **Input**          | **Description** | **Default** | **Required** |
| :----------------- | :-------------- | :---------: | :----------: |
| **`who-to-greet`** | Who to greet    |   `World`   |   **true**   |

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
      - 'chart/**'
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
