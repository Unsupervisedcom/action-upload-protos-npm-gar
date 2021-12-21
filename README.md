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
- uses: Unsupervisedcom/action-composite-action-template@undefined
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

### Example usage with npm upload protos action, will result in an uploaded package called `@unsupervised/my-app`

```yaml
name: Build and upload npm protos to gar
on:
  release:
    types: [created]
jobs:
  build-upload-protos-npm:
    runs-on: ubuntu-latest
    steps:
      - uses: Unsupervisedcom/action-buf-generate@v1
      - uses: Unsupervisedcom/action-upload-protos-npm-gar@v1
        with:
          project-id: ${{ secrets.GOOGLE_ARTIFACT_PROJECT_ID }}
          credentials-json: ${{ secrets.GOOGLE_ARTIFACT_READ_WRITE }}
          package-name: 'my-app'
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
