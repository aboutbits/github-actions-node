# GitHub Actions Node

A collection of GitHub actions for Node projects.

## Actions

### Setup Node

This action will set up Node.js.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/setup@v3
    with:
      node-version: 22
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                               |
|---------------------|------------------|-------------------------------------------|
| `working-directory` | `.`              | The working directory of the action       |
| `node-version`      | `22`             | The Node.js version that should be set up |
| `registry-url`      | (empty)          | Optional registry to set up for auth      |

### Setup Node and Install Dependencies

This action will set up Node.js and install all NPM dependencies.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/setup-and-install@v3
    with:
      node-version: 22
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                               |
|---------------------|------------------|-------------------------------------------|
| `working-directory` | `.`              | The working directory of the action       |
| `node-version`      | `22`             | The Node.js version that should be set up |
| `registry-url`      | (empty)          | Optional registry to set up for auth      |

### Build and Release Package

This action will build and release an NPM package.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/build-and-publish-package@v3
    with:
      version: AboutBits
      git-user-email: info@aboutbits.it
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                                                                                |
|---------------------|------------------|--------------------------------------------------------------------------------------------|
| `working-directory` | `.`              | The working directory of the action                                                        |
| `node-version`      | `22`             | The Node.js version that should be set up                                                  |
| `registry-url`      | (empty)          | Optional registry to set up for auth                                                       |
| `increment`         | required         | The version increment type (major, minor, patch, prerelease, premajor, preminor, prepatch) |
| `preid`             | (empty)          | The prerelease identifier (only required if increment is premajor, preminor or prepatch)   |

## Versioning

In order to have a verioning in place and working, create leightweight tags that point to the appropriate minor release versions.

Creating a new minor release:

```bash
git tag v3
git push --tags
```

Replacing an already existing minor release:

```bash
git tag -d v3
git push origin :refs/tags/v3
git tag v3
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
