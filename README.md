# CommitLint Config

[`commitlint`](https://github.com/conventional-changelog/commitlint) config.

## Install

You need to create a `.npmrc` file and add the following lines:

```
registry=https://registry.npmjs.org/
@vinicius-arcanjo:registry=https://npm.pkg.github.com
```

You can install it with npm, yarn or pnpm.

```sh
# npm
npm i -D @vinicius-arcanjo/commitlint-config @commitlint/cli

# Yarn
yarn add -D @vinicius-arcanjo/commitlint-config @commitlint/cli

# Pnpm
pnpm add -D @vinicius-arcanjo/commitlint-config @commitlint/cli
```

## Usage

After installing it, apply the config to `commitlint` by running the following command:

```sh
echo "module.exports = { extends: ['@vinicius-arcanjo/commitlint-config'] };" > .commitlintrc.js
```

## Husky

To lint commits before they are created, install Husky and use the 'commit-msg' hook.

```sh
# Npm
npm i -D husky

# Yarn
yarn add -D husky

# Pnpm
pnpm add -D husky
```

After that, add to your `package.json` the following code for

```json
{
  "lint-staged": {
    "src/**/*": [
      "pnpm lint --fix",
      "pnpm test --findRelatedTests --bail"
    ]
  }
}
```

Husky:

```sh
# Npm
npx husky-init

# Yarn
yarn dlx husky-init --yarn2

# Pnpm
pnpm dlx husky-init
```

After that

```sh
npx husky add .husky/commit-msg 'npx --no -- commitlint --edit "$1"'
```

And then edit the `.husky/pre-commit`

```sh
#lint stage
npx --no-install lint-staged
```


## Version Support

- Node.js [LTS](https://github.com/nodejs/LTS#lts-schedule) `>= 10.21.0`
- git `>= 2.13.2`

## Contributing

Contributions are always welcome! If you wish to add new features or enhance the existing templates, please create a pull request to the appropriate branch.

## License

This project is under the [MIT License ©](https://github.com/vinicius-arcanjo/commitlint-config/blob/main/LICENSE.md). See the `LICENSE` file in each branch for more details.
