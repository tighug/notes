# Webpack

Webpack とは、**Web アプリを作成する際に複数のコンテンツファイル（主に JavaScript）を 1 つにまとめるツール**です。ブラウザとサーバー間のリクエスト数が減少し、ファイルの転送が高速となります。CSS や画像もバンドル可能です。

- [最新版で学ぶ webpack 4 入門 JavaScript のモジュールバンドラ](https://ics.media/entry/12140/)

## Installation

本体の`webpack`と、コマンド実行用の`webpack-cli`を `devDependecies`にインストールします。

```bash
yarn add -D webpack webpack-cli
```

ローカルサーバーを立てたい時は`webpack-dev-server`もインストールします。

```bash
yarn add -D webpack-dev-server
```

## Config - `webpack.config.js`

```JS
module.exports = {
  target: 'node',
  mode: "development",
  entry: {
    main: "./src/3_adapters/main.ts",
    server: "./src/4_frameworks/server.ts"
  },
  output: {
    path: `${__dirname}/build`,
    filename: "[name].js"
  },
  module: {
    rules: [
      { test: /\.ts$/, exclude: /node_modules/, use: "ts-loader" }
    ]
  },
  // import 文で .ts ファイルを解決するため
  resolve: {
    extensions: [".ts", ".js"],
  },
  // webpack-dev-serverを使う場合
  devServer: {
    contentBase: path.join(__dirname, 'build/public'),
    inline: true,
    watchContentBase: true,
    open: true
  }
};
```

### 詳細

| name         | description                                                              |
| ------------ | ------------------------------------------------------------------------ |
| `target`     | Nodejs なら`node`、Browser なら`web`                                     |
| `mode`       | 開発時（ソースマップ有効）は `development`、`production`は公開時（圧縮） |
| `entry`      | エントリーポイント                                                       |
| `output`     |                                                                          |
| - `path`     | 出力ディレクトリのパス                                                   |
| - `filename` | 出力ファイル名                                                           |
| `module`     |                                                                          |
| - `rules`    |                                                                          |
| -- `test`    | 対象とする拡張子（e.g. `/\.ts$/`）                                       |
| -- `use`     | 使用するローダー（e.g. `ts-loader`）                                     |
| `plugin`     | 使用するプラグイン                                                       |

#### よく使うプラグイン

| name                         | description                                                          |
| ---------------------------- | -------------------------------------------------------------------- |
| `HotModuleReplacementPlugin` | ホットリロードを有効にする                                           |
| `HtmlWebpackPlugin`          | バンドルを提供する HTML ファイルを簡単に作成する                     |
| `CopyWebpackPlugin`          | 個々のファイルまたはディレクトリ全体をビルドディレクトリにコピーする |
