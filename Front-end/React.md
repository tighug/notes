# React

## Installation

### Boilerplate

`react-scripts`により、Babel や Webpack の設定無しですぐに開発を始められます。SPA を作成したい場合は最良の方法です。

```bash
yarn create react-app [project name]

# TypeScriptを利用する場合（推奨）
yarn create react-app [project name] --typescript typescript
```

### From scratch

各パッケージのインストールに加え、Babel や Webpack、TypeScript の設定を手動で行います。独自の設定をしたい場合や、Electron などのほかのツールと組み合わせる場合に利用します。

```bash
yarn add -D react react-dom
```
