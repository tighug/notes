# Prettier / ESLint

Prettierとは、**コードフォーマッター**で、Javascript や、CSS、Markdown 等に対応しています。
ESLintとは、**JavaScript のための静的検証ツール**です。

ESLint もフォーマット機能を持っていますが、Prettier の方が優れています。
その為、**フォーマットは Prettier** が行い、**構文チェックは ESLint** が行うように併用します。

- [Prettier 入門 ～ ESLint との違いを理解して併用する～ - Qiita](https://qiita.com/soarflat/items/06377f3b96964964a65d)

## Installation

```bash
yarn add -D eslint
yarn add -D prettier
yarn add -D eslint-config-prettier
yarn add -D eslint-plugin-prettier
```

- `eslint-config-prettier`
  - ESLint のフォーマット関連のルールを全て無効にする
  - つまり Prettier が整形した箇所に関してエラーを出さなくなる
- `eslint-plugin-prettier`
  - Prettier を ESLint 上で実行する

### Typescript に対応させる

上記に加え、以下もインストールします。

```bash
yarn add -D @typescript-eslint/eslint-plugin
yarn add -D @typescript-eslint/parser
```

## Config

### `.eslintrc`

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:prettier/recommended",
    "prettier/@typescript-eslint"
  ],
  "plugins": ["@typescript-eslint"],
  "parser": "@typescript-eslint/parser",
  "env": {
    "browser": true,
    "node": true,
    "es6": true
  },
  "parserOptions": {
    "sourceType": "module"
  },
  "rules": {
    "prettier/prettier": "error"
  }
}
```

### `.prettierrc`

| option                    | default     | description                                          |
| ------------------------- | ----------- | ---------------------------------------------------- |
| printWidth                | 80          | 折り返す行の長さ                                     |
| tabWidth                  | 2           | タブ幅                                               |
| useTabs                   | false       | スペースではなくタブでインデントする                 |
| semi                      | true        | ステートメントの最後にセミコロンを記述する           |
| singleQuote               | false       | 二重引用符の代わりに単一引用符を使用する             |
| quoteProps                | "as-needed" | オブジェクトのプロパティに引用符を付けるか           |
| jsxSingleQuote            | false       | JSX で、二重引用符の代わりに単一引用符を使用する     |
| trailingComma             | "none"      | 複数行の場合、可能な鍵地末尾のコンマを記述する       |
| bracketSpacing            | true        | オブジェクトリテラルの各カッコの間にスペースを入れる |
| jsxBracketSameLine        | false       | JSX のブラケットを最後の行の末尾に置く               |
| arrowParens               | "avoid"     | アロー関数の引数をカッコで囲むか                     |
| rangeStart                | 0           |                                                      |
| rangeEnd                  | Infinity    |                                                      |
| parser                    | -           | 使用するパーサー                                     |
| filepath                  | -           | 使用するファイル                                     |
| requirePragma             | false       | プラグマが必要か                                     |
| insertPragma              | false       | プラグマを挿入するか                                 |
| proseWrap                 | "preserve"  |                                                      |
| htmlWhitespaceSensitivity | "css"       |                                                      |
| endOfLine                 | "auto"      | 行末                                                 |
