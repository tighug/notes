# TypeScript

TypeScript とは、**静的型付きプログラミング言語であり、Alt JavaScript 言語の 1 つ**です。コンパイルすることで JavaScript が生成されます。

## Installation

```bash
yarn add -D typescript
```

### webpack と併用する場合

`ts-loader`をインストールします。

```bash
yarn add -D ts-loader
```

webpack.config.js に以下を追加します。

```js
module.exports = {
  resolve: {
    //拡張子がtsだったらTypescirptでコンパイルする
    extensions: [".ts", ".js"]
  },
  module: {
    rules: [{ test: /\.ts$/, loader: "ts-loader" }]
  }
};
```

## Config - `tsconfig.json`

```json
{
  "compilerOptions": {
    "strict": true,
    "sourceMap": true,
    "target": "ES6", // ES5かES6
    "module": "Commonjs", // targetがES5ならCommonjs、ES6ならES6
    "moduleResolution": "Node" // NodejsならNode、BrowserならClassic
  },
  // コンパイルするファイル
  "include": ["src/**/*"],
  // コンパイルしないファイル
  "exclude": ["node_modules", "**/*.spec.ts"]
}
```

### CompilerOptions

使いそうなものを抜粋。

| Option                       | Default | Description                                              |
| ---------------------------- | ------- | -------------------------------------------------------- |
| allowJs                      | false   | JavaScript をコンパイルできるようにする。                |
| checkJs                      | false   | JS のエラーも指摘する。allowJs と併用する。              |
| strict                       | false   | 厳密な型チェックオプションを**全て**有効にする。         |
| sourceMap                    | false   | デバッガーに`.js`ではなく、`.ts` を参照させる。          |
| target                       | "ES3"   | トランスパイル後の ECMAScript のターゲットのバージョン。 |
| module                       |         | 生成されるモジュールの種類を指定する。                   |
| moduleResolution             |         | モジュールの解決方法を指定する。                         |
| resolveJsonModule            | false   | JSON のインポートを認める。                              |
| esModuleInterop              | false   | Babel との互換性を可能にする。                           |
| allowSyntheticDefaultImports | false   | import/export の互換性を緩くする。                       |

## 型定義ファイル`.d.ts`

外部モジュールのインポート時に、エラーが出る場合。これは、そのモジュールが TypeScipt で利用されることを想定しておらず、TypeScript 用の型定義ファイルが不足しているからである。以下で型定義ファイルをインストールするか、`require`を使うことでエラーを解消できる。

```bash
yarn add -D @types/[moduleName]
```
