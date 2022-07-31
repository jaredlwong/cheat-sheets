asdf install nodejs 18.7.0
asdf local nodejs 18.7.0
npm init
npm install typescript @types/node --save-dev

# [tsconfig](https://www.typescriptlang.org/tsconfig)
npx tsc --init --lib esnext --target esnext --module commonjs --inlineSourceMap true --inlineSources true --outDir dist

# eslint for typescript
npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin

## .eslintrc.json
```json
{
  "root": true,
  "parser": "@typescript-eslint/parser",
  "plugins": [
    "@typescript-eslint"
  ],
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended"
  ],
  "ignorePatterns": ["**/*.js"]
}
```
