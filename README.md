# GitHub Action: Setup Go

- Installs Go
- Sets up cache for:
  - `GOCACHE`
  - `GOMODCACHE`
- Sets up access for private modules

## Usage

### Inputs

| label           | default | required | description                             |
| --------------- | ------- | -------- | --------------------------------------- |
| go-version      |         | No       | The Go version to use.                  |
| stable          | true    | Yes      | Use only stable version.                |
| ssh-private-key |         | No       | SSH key to access private repositories. |

## Example

```yaml
jobs:
  docker-pull:
    runs-on: ubuntu-latest
    steps:
    - uses: RallyGo/action-setup-go@v0
      with:
        go-version: '^1.17'
        ssh-private-key: ${{ secrets.GLOBAL_GITHUB_SSH_KEY }}
    - run: go version
```
