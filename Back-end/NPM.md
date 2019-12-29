# NPM

Yarn とは、**Node.js のパッケージマネージャ**です。`npm`よりも高速です。

- [npm と yarn のコマンド早見表](https://qiita.com/rubytomato@github/items/1696530bb9fd59aa28d8)

## Installation

[Node.js](./Nodejs.md)のインストールを参照して下さい。

## Usage

| command                      | description                                           |
| ---------------------------- | ----------------------------------------------------- |
| `npm init`                   | カレントディレクトリの管理を開始。                    |
| `npm ls -g --depth=0`        | インストールパッケージ一覧（global）                  |
| `npm ls --depth=0`           | インストールパッケージ一覧                            |
| `npm install -g [package]`   | パッケージをインストール（global）                    |
| `npm install`                | `package.json`に記録されたパッケージをインストール    |
| `npm install -S [package]`   | インストールと同時に`dependencies`に記録              |
| `npm intall -D [package]`    | インストールと同時に`devDependencies`に記録           |
| `npm uninstall -g [package]` | パッケージをアンインストール（global）                |
| `npm unintall -S [package]`  | アンインストールと同時に`dependencies`の記録を削除    |
| `npm unintall -D [package]`  | アンインストールと同時に`devDependencies`の記録を削除 |
| `npm update -g`              | パッケージ全てを更新（global）                        |
| `npm update -g [package]`    | 指定したパッケージを更新（global）                    |
| `npm update`                 | パッケージ全てを更新                                  |
| `npm update [package]`       | 指定したパッケージを更新                              |
| `npm run`                    | スクリプトの一覧を表示                                |
| `npm run run [script]`       | `package.json`の`script`に定義されたスクリプトを実行  |
| `npm run env`                | 環境変数の表示                                        |

## package.json

※マークは必須。
| setting | description |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **name**※ | モジュールの名前。 |
| **version**※ | モジュールのバージョン。 |
| **private** | `true`ならモジュールを公開ができない。 |
| **description** | モジュールの説明。 |
| **main** | モジュールの中で最初に呼ばれるスクリプトファイル。 |
| **scripts** | 任意のシェルスクリプトを実行するエイリアスを定義できる。「dependencies」や「devDependencies」に入っているモジュールは自動的に PATH に入る。 |
| **repository** | ソースコードが管理されている場所を指定。 |
| **author** | 作者 |
| **license** | ライセンス情報 |
| **bugs** | プロジェクトの問題やバグ追跡を見る url とそれらの報告を行う email アドレス |
| **homepage** | プロジェクトのホームページ URL。 |
| **dependicies** | モジュール実行時に依存するモジュールとバージョンを記述する。インストール時には`--save`もしくは`-S`オプションを付けると、同時に記述される。`npm i --save [packageName]` |
| **devDependecies** | モジュール開発時に依存するモジュールとバージョンを記述する。 インストール時には`--save-dev`もしくは`-D`オプションを付けると、同時に記述される。`npm i --save-dev [packageName]` |
| **jest** | jest の設置を記述する。 |
