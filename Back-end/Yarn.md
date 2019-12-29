# Yarn

Yarn とは、**Node.js のパッケージマネージャ**です。`npm`よりも高速です。

- [npm と yarn のコマンド早見表](https://qiita.com/rubytomato@github/items/1696530bb9fd59aa28d8)

## Installation

npm 経由でインストール

```bash
sudo npm i -g yarn
```

## Usage

| command                         | description                                          |
| ------------------------------- | ---------------------------------------------------- |
| `yarn init`                     | カレントディレクトリの管理を開始。                   |
| `yarn global list --depth=0`    | インストールパッケージ一覧（global）                 |
| `yarn list --depth=0`           | インストールパッケージ一覧                           |
| `yarn global add [package]`     | パッケージをインストール（global）                   |
| `yarn install`                  | `package.json`に記録されたパッケージをインストール   |
| `yarn add [package]`            | インストールと同時に`dependencies`に記録             |
| `yarn add --dev [package]`      | インストールと同時に`devDependencies`に記録          |
| `yarn global remove [package]`  | パッケージをアンインストール（global）               |
| `yarn remove [package]`         | アンインストールと同時に`package.json`の記録を削除   |
| `yarn global upgrade`           | パッケージ全てを更新（global）                       |
| `yarn global upgrade [package]` | 指定したパッケージを更新（global）                   |
| `yarn upgrade`                  | パッケージ全てを更新                                 |
| `yarn upgrade [package]`        | 指定したパッケージを更新                             |
| `yarn run`                      | スクリプトの一覧を表示                               |
| `yarn run [script]`             | `package.json`の`script`に定義されたスクリプトを実行 |
| `yarn run env`                  | 環境変数の表示                                       |
