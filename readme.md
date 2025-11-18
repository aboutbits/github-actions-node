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

### Configure GitHub NPM Registry Access

This action will set up the access to the GitHub NPM registry.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/configure-github-npm-registry-access@v3
```

### Configure GitHub NPM Registry Organization

This action will point an NPM organization to the GitHub NPM registry.

#### Example

```yaml
  - uses: aboutbits/github-actions-node/configure-github-npm-registry-organization@v3
    with:
      organization: aboutbits
```

#### Inputs

The following inputs can be used as `step.with` keys:

| Name           | Required/Default | Description          |
|----------------|------------------|----------------------|
| `organization` | `aboutbits`      | The NPM organization |

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
| `registry-url`      | (empty)          | Optional registry url for auth                                                             |
| `registry-token`    | (empty)          | Optional registry token for auth                                                           |
| `increment`         | required         | The version increment type (major, minor, patch, prerelease, premajor, preminor, prepatch) |
| `preid`             | (empty)          | The prerelease identifier (only required if increment is premajor, preminor or prepatch)   |

#### Outputs

The following outputs are forwarded from the underlying actions:

| Name      | Description                                |
|-----------|--------------------------------------------|
| `name`    | The package name of the package.json file. |
| `version` | The new package version.                   |

## Build & Publish

To build and publish the action, visit the GitHub Actions page of the repository and trigger the workflow "Release Package" manually.

## Information

About Bits is a company based in South Tyrol, Italy. You can find more information about us on [our website](https://aboutbits.it).

### Support

For support, please contact [info@aboutbits.it](mailto:info@aboutbits.it).

### Credits

- [All Contributors](../../contributors)

### License

The MIT License (MIT). Please see the [license file](license.md) for more information.
