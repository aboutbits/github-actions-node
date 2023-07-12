# GitHub Actions Node

A collection of GitHub actions for Node projects.

## Setup Node and Install Dependencies

This action will set up Node.js and install all NPM dependencies.

### Example

```yaml
  - uses: actions/checkout@v3

  - uses: aboutbits/github-actions-node/setup-and-install@v1
    with:
      node-version: 16
```

## Test

This action will first run the setup and install action and then execute the tests.

### Example

```yaml
  - uses: actions/checkout@v3

  - uses: aboutbits/github-actions-node/test@v1
    with:
      node-version: 16
```

## Lint

This action will first run the setup and install action and then lint the code.

### Example

```yaml
  - uses: actions/checkout@v3

  - name: 
    uses: aboutbits/github-actions-node/lint@v1
    with:
      node-version: 16
```

## Typecheck

This action will first run the setup and install action and then typecheck the code.

### Example

```yaml
  - uses: actions/checkout@v3

  - name: 
    uses: aboutbits/github-actions-node/typecheck@v1
    with:
      node-version: 16
```

## Versioning

In order to have a verioning in place and working, create leightweight tags that point to the appropriate minor release versions.

Creating a new minor release:

```bash
git tag v1
git push --tags
```

Replacing an already existing minor release:

```bash
git tag -d v1
git push origin :refs/tags/v1
git tag v1
git push --tags
```

## Information

About Bits is a company based in South Tyrol, Italy. You can find more information about us on [our website](https://aboutbits.it).

### Support

For support, please contact [info@aboutbits.it](mailto:info@aboutbits.it).

### Credits

- [All Contributors](../../contributors)

### License

The MIT License (MIT). Please see the [license file](license.md) for more information.
