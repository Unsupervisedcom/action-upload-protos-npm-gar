<!-- start title -->

# GitHub Action:Generate and upload npm protos

<!-- end title -->
<!-- start description -->

Generates npm protos and uploads them to google artifact registry

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: Unsupervisedcom/action-upload-protos-npm-gar@undefined
  with:
    # Google credentials json
    credentials-json: ""

    # Google cloud project id
    project-id: ""

    # NPM package name
    package-name: ""

    # Version to publish
    # Default: ${{ github.event.release.tag_name }}
    version: ""

    # Artifact registry scope
    # Default: @unsupervised
    scope: ""

    # Artifact registry repository name
    # Default: npm
    repository: ""

    # Artifact registry location
    # Default: us-central1
    location: ""

    # Location of generated protos
    # Default: build/nodejs
    proto-directory: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**              | **Description**                   |              **Default**               | **Required** |
| :--------------------- | :-------------------------------- | :------------------------------------: | :----------: |
| **`credentials-json`** | Google credentials json           |                                        |   **true**   |
| **`project-id`**       | Google cloud project id           |                                        |   **true**   |
| **`package-name`**     | NPM package name                  |                                        |   **true**   |
| **`version`**          | Version to publish                | `${{ github.event.release.tag_name }}` |  **false**   |
| **`scope`**            | Artifact registry scope           |            `@unsupervised`             |  **false**   |
| **`repository`**       | Artifact registry repository name |                 `npm`                  |  **false**   |
| **`location`**         | Artifact registry location        |             `us-central1`              |  **false**   |
| **`proto-directory`**  | Location of generated protos      |             `build/nodejs`             |  **false**   |

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
          package-name: "my-app"
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
