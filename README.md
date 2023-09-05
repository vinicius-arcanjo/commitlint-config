# @vinicius-arcanjo/commitlint-config



[`commitlint`](https://github.com/conventional-changelog/commitlint) config.

## Install

You can install it with npm or Yarn.

```sh
# npm
npm i -D @vinicius-arcanjo/eslint-config @commitlint/cli

# Yarn
yarn add -D @vinicius-arcanjo/eslint-config @commitlint/cli
```

## Usage

After installing it, apply the config to `commitlint` by running the following command:

```sh
echo "module.exports = { extends: ['@vinicius-arcanjo/commitlint-config'] };" > .commitlintrc.js
```

## Bonus

To lint commits before they are created, install Husky and use the 'commit-msg' hook.

```sh
# Npm
npm i -D husky

# Yarn
yarn add -D husky
```

After that, you can create a `.huskyrc` file or add to your `package.json` the following code for

Husky v4:

```json
{
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}
```

Husky v5:

```
# .husky/commit-msg
# ...
npx --no-install commitlint --edit $1
# or
yarn commitlint --edit $1
```

## Version Support

- Node.js [LTS](https://github.com/nodejs/LTS#lts-schedule) `>= 10.21.0`
- git `>= 2.13.2`

## License

MIT License © [Link](https://github.com/vinicius-arcanjo/commitlint-config/blob/main/LICENSE.md)
