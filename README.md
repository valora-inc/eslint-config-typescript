# @valora/eslint-config-typescript

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

## Publishing

Run `yarn release` and follow the instructions.
