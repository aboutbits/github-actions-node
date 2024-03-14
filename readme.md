# GitHub Actions Node

A collection of GitHub actions for Node projects.

## Actions

### Setup Node

This action will set up Node.js.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/setup@v2
    with:
      node-version: 20
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                               |
|---------------------|------------------|-------------------------------------------|
| `working-directory` | `.`              | The working directory of the action       |
| `node-version`      | `20`             | The Node.js version that should be set up |
| `registry-url`      | (empty)          | Optional registry to set up for auth      |

### Setup Node and Install Dependencies

This action will set up Node.js and install all NPM dependencies.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/setup-and-install@v2
    with:
      node-version: 20
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                               |
|---------------------|------------------|-------------------------------------------|
| `working-directory` | `.`              | The working directory of the action       |
| `node-version`      | `20`             | The Node.js version that should be set up |
| `registry-url`      | (empty)          | Optional registry to set up for auth      |

### Create a new NPM version

This action will set up git, increment the NPM version and push the changes.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/version@v2
    with:
      git-user-name: AboutBits
      git-user-email: info@aboutbits.it
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name                | Required/Default | Description                               |
|---------------------|------------------|-------------------------------------------|
| `working-directory` | `.`              | The working directory of the action       |
| `git-user-name`     | Required         | The name of the git user                  |
| `git-user-email`    | Required         | The email of the git user                 |
| `version`           | `patch`          | The version that should be set            |
| `message`           | `[RELEASE] %s`   | The message of the git commit             |

## Versioning

In order to have a verioning in place and working, create leightweight tags that point to the appropriate minor release versions.

Creating a new minor release:

```bash
git tag v2
git push --tags
```

Replacing an already existing minor release:

```bash
git tag -d v2
git push origin :refs/tags/v2
git tag v2
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
