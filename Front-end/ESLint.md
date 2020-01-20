# ESLint

ESLint とは、**JavaScript のための静的検証ツール**の一つです。

- [Prettier 入門 ～ ESLint との違いを理解して併用する～ - Qiita](https://qiita.com/soarflat/items/06377f3b96964964a65d)

## Installation

```bash
yarn add -D eslint
```

## Usage

`extends`

拡張したい機能を記述します。[Extends](#Extends)を参照して下さい。

`plugins`

使用したいプラグインを記述します。大体`extends`と関係します。[Extends](#Extends)を参照して下さい。

`parser`

使用したいパーサーを記述します。TypeScript や Babel 等、使いたい言語に合わせて変更します。

### `parseOptions`

ES6 の`import/export`を使いたい場合、以下で ES Modules 機能を有効にします。

```json
{
  "parserOptions": {
    "sourceType": "module"
  }
}
```

### `env`

最低限、以下の 3 つを設定します。他は`extends`で`recommended`を選択すると大体自動で設定してくれます。

```json
{
  "env": {
    "browser": true, // ブラウザで実行する
    "node": true, // Node.jsで実行する
    "es6": true // ES6を使用する
  }
}
```

### `rules`

ルールを上書きできます。できる限り`extends`の`recommended`を採用したいので、あまり記述しません。

## Extends

プロジェクトで用いる言語やツールにに応じて拡張を行います。

### Prettier

Prettier とは、**コードフォーマッター**の一つです。Javascript や、CSS、Markdown 等に対応しています。ESLint もフォーマット機能を持っていますが、Prettier の方が優れています。そのため、**フォーマットは Prettier** 、**構文チェックは ESLint** が行うように併用します。

```bash
yarn add -D prettier eslint-config-prettier eslint-plugin-prettier
```

- `prettier`：Prettier 本体
- `eslint-config-prettier`：Prettier と競合するルールを無効にする設定
- `eslint-plugin-prettier`：ESLint のフォーマットに Prettier を用いるプラグイン

また、`.eslintrc.json`に以下を記述することで、3 つの設定を一度に行います。

1. `eslint-plugin-prettier`を有効に
2. `rule`に`prettier/prettier: "error"`を設定
3. `eslint-config-prettier`を拡張

```json
{
  "extends": ["plugin:prettier/recommended"]
}
```

**※ ルールを優先させるため、Prettier 系の`extends`はできるだけ後ろに記述して下さい**

### Node.js

```bash
yarn add -D eslint-plugin-node
```

- `eslint-plugin-node`：Node.js 用意のルールを追加するプラグイン

`.eslintrc.json`には以下を記述します。

```json
{
  "extends": ["plugin:node/recommended"]
}
```

### TypeScript

```bash
yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

- `@typescript-eslint/parser`：ESLint が TypeScript をリントするためのパーサー
- `@typescript-eslint/eslint-plugin`：TypeScript 用のルールを追加するプラグイン

`.eslintrc.json`には以下を記述します。

```json
{
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"],
  "extends": [
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:prettier/recommended" // Prettierも使う場合
  ]
}
```

### Vue.js

```bash
yarn add -D eslint-plugin-vue
```

- `eslint-plugin-vue`：Vue.js 用のルールを追加するプラグイン

`.eslintrc.json`には以下を記述します。

```json
{
  "extends": ["plugin:vue/recommended"]
}
```

### Jest

```bash
yarn add -D eslint-plugin-jest
```

- `eslint-plugin-jest`：Jest 用のルールを追加するプラグイン

`.eslintrc.json`には以下を記述します。

```json
{
  "extends": ["plugin:jest/recommended"]
}
```

## Config

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
