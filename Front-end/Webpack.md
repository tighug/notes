# Webpack

Webpack とは、**複数のモジュールを一つのファイルにまとめるツール**です。自動的にモジュールの依存関係を解決します。また、一つにまとめることで Web サーバーへのリクエスト回数を減らせます。

## Installation

```bash
yarn add -D webpack webpack-cli
```

- `webpack` : 本体
- `webpack-cli` : CLI ツール

## CLI

```bash
webpack-cli init  # webpack.config.jsを生成する

webpack --config [config file]
```

## Configuration

Ref : [Webpack Configuration](https://webpack.js.org/configuration/)

`webpack.config.js`に記述します。

### `mode`

最適化モード
`"production" | "development" | "none"`

### `context`

ベースディレクトリ（デフォルトは 現在のディレクトリ）。絶対パスで指定
`string`

### `entry`

バンドルプロセスを開始するポイント。配列やオブジェクトが渡せば、複数のアイテムを処理可能
`string | object | array`

### `output`

出力する方法と場所
`string | object`

- `path` : 出力先のディレクトリのパス。絶対パス
- `filename` : 出力ファイル名

### `module`

異なるタイプのモジュールの扱われ方。主に`rules`を記述する

- `rules`
  - `test` : 対象とするファイル。RegExp で記述
  - `include` : 対象とするディレクトリ
  - `exclude` : 非対象とするディレクトリ
  - `use` : 使用するローダー

### `resolve`

モジュールの解決方法
`object`

- `extensions` : 拡張子を省略して`import`に記述する

### `target`

対象とする実行環境
`string | function(compiler)`

#### string options

- `node` : Node.js 用
- `web` : ブラウザ用
- `electron-main` : Electron のメインプロセス用
- `electron-renderer` : Electron のレンダラープロセス用
- `electron-preload` : Electron のレンダラープロセス用（preload）

### `plugins`

使用するプラグイン
`[Plugin]`

## Plugins

Ref : [Webpack Plugins](https://webpack.js.org/plugins/)

よく使うものを抜粋しました。

- `HotModuleReplacementPlugin` : HMR を有効にする
- `HtmlWebpackPlugin` : バンドルを提供する HTML ファイルを簡単に作成する
- `CopyWebpackPlugin` : 個々のファイルまたはディレクトリ全体をビルドディレクトリにコピーする

## Loaders

Ref : [Webpack Loaders](https://webpack.js.org/loaders/)

- `babel-loader` : JavaScript
- `ts-loader` : TypeScript
- `css-loader` : CSS
- `eslint-loader` : ESLint

## Example

```js
module.exports = {
  target: "node",
  mode: "development",
  entry: {
    main: "./src/main.ts",
    server: "./src/server.ts",
  },
  output: {
    path: `${__dirname}/build`,
    filename: "[name].js",
  },
  module: {
    rules: [{ test: /\.ts$/, exclude: /node_modules/, use: "ts-loader" }],
  },
  resolve: {
    extensions: [".ts", ".js"],
  },
};
```

## Tips

### 開発用のローカルサーバーを立てる

- [Webpack Dev Server](./WebpackDevServer.md)

## References

- [Webpack](https://webpack.js.org/)
- [最新版で学ぶ webpack 4 入門 JavaScript のモジュールバンドラ](https://ics.media/entry/12140/)
