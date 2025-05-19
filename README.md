# Action Golang with `golangci-lint`

GitHub Action for setting up Golang via [actions/setup-go](https://github.com/actions/setup-go) coupled with [golangci/golangci-lint-action](https://github.com/golangci/golangci-lint-action) for source linting.

At completion of Action, runner will be left with the desired Golang version, ready for running additional quality of life operations - such as `go test`.

**Note:** internally, [golangci/golangci-lint-action](https://github.com/golangci/golangci-lint-action) provides caching of the Golang build and module cache directories - so no requirement to handle this from within the composite action itself.

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
          version-golang-file: go.mod
          # alternatively, use `version-golang` input
          #version-golang: ~1.24
          version-golangci-lint: v2.1.6
```
