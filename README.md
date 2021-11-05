# Action Golang with `golangci-lint`

GitHub Action for setting up Golang via [actions/setup-go](https://github.com/actions/setup-go) coupled with [golangci/golangci-lint-action](https://github.com/golangci/golangci-lint-action) for source linting.

At completion of Action, runner will be left with the desired Golang version, ready for running additional quality of life operations - such as `go test`.

**Note:** internally, the [golangci/golangci-lint-action](https://github.com/golangci/golangci-lint-action) action provides caching of the Golang build/module cache directories - so no requirement to handle this within the composite action.

## Usage

```yaml
jobs:
  main:
    name: Use Golang
    runs-on: ubuntu-latest
    steps:
      - name: Setup Golang with lint
        uses: flipgroup/action-golang-with-lint@main
        with:
          version-golang: ~1.17
          version-golangci-lint: v1.43.0
```
