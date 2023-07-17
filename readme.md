# GitHub Actions Node

A collection of GitHub actions for Node projects.

## Actions

### Setup Node

This action will set up Node.js.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/setup@v1
    with:
      node-version: 16
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                               |
|---------------------|------------------|-------------------------------------------|
| `working-directory` | `.`              | The working directory of the action       |
| `node-version`      | `16`             | The Node.js version that should be set up |

### Setup Node and Install Dependencies

This action will set up Node.js and install all NPM dependencies.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/setup-and-install@v1
    with:
      node-version: 16
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                               |
|---------------------|------------------|-------------------------------------------|
| `working-directory` | `.`              | The working directory of the action       |
| `node-version`      | `16`             | The Node.js version that should be set up |

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
