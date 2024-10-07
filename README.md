# @valora/eslint-config-typescript

[![GitHub License](https://img.shields.io/github/license/valora-inc/eslint-config-typescript?color=blue)](https://github.com/valora-inc/eslint-config-typescript/blob/main/LICENSE)
[![npm version](https://img.shields.io/npm/v/@valora/eslint-config-typescript.svg)](https://www.npmjs.com/package/@valora/eslint-config-typescript)
[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/valora-inc/eslint-config-typescript/Workflow/main)](https://github.com/valora-inc/eslint-config-typescript/actions/workflows/workflow.yaml?query=branch%3Amain)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/valora-inc/eslint-config-typescript#contributing)

Shareable ESLint config for Valora TypeScript packages.

## Installing

Add the ESLint config in your package:

```
yarn add @valora/eslint-config-typescript --dev
```

and add all the [`peerDependencies`](./package.json).

## Using

Add a script to your package.json like:

```json
{
  "scripts": {
    "lint": "eslint --ext=.tsx,.ts src/"
  }
}
```

and create a `.eslintrc.js` file:

```js
module.exports = {
  extends: ['@valora/eslint-config-typescript'],
  // The @typescript-eslint/no-floating-promises and @typescript-eslint/no-misused-promises
  // plugins require a full compilation, so pass the `tsconfig.json` config file.
  parserOptions: {
    project: './tsconfig.json',
  },
  ignorePatterns: ['**/__mocks__/**', '**/lcov-report/**', 'vendor', '.bundle'],
}
```

## Resources

ESLint [Shareable Configs](https://eslint.org/docs/developer-guide/shareable-configs).

## Contributing

- [Reporting issues](https://github.com/valora-inc/eslint-config-typescript/issues)
- [Submitting a pull request](https://github.com/valora-inc/eslint-config-typescript/pulls)
- Publishing updates is done automatically via [semantic-release](https://github.com/semantic-release/semantic-release).
  Remember to use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) or your PR will be rejected (since
  merging it would mess up the changelog and version numbers).
