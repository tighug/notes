# Docker Compose

docker-compose を使うと、複数のコンテナから構成されるサービスを簡単に管理できます。

## Installation

### Linux & Mac

#### 1. ダウンロード

`1.25.0`の部分は、最新のものに書き換える。

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.25.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

#### 2. パーミッションの修正

```bash
sudo chmod +x /usr/local/bin/docker-compose
```

## コマンド

| command   | description                           |
| --------- | ------------------------------------- |
| `build`   | サービスのイメージをビルドする。      |
| `restart` | サービスを再起動する。                |
| `run`     | サービスを起動する。                  |
| `up`      | サービスのイメージをビルド&起動する。 |
| `exec`    | サービスに対してコマンドを実行する。  |
| `logs`    | サービスのログを出力する。            |
| `stop`    | サービスを停止させる。                |
| `kill`    | サービスを kill する。                |

### build

```bash
docker-compose build    // 全てのサービスをビルド
docker-compose build db // サービスを指定してビルド
```

### start

```bash
docker-compose start        // 全てのサービスを起動
docker-compsoe start rails  // サービスを指定して起動
```

### up

```bash
docker-compose up     // 全てのサービスをビルド&起動
docker-compose up -d  // バックグラウンドでビルド&起動
docker-compose up rails // サービスを指定してビルド&起動
```

### exec

```bash
docker-compose exec [SERVICE] [COMMAND]
docker-compose run [SERVICE] [COMMAND]
```

※ `exec`は既に立ち上がっているコンテナを実行。`run`は新しくコンテナを立ち上げて実行。

### logs

```bash
docker-compose logs       # 全てのサービスのログを出力
docker-compose logs rails # サービス指定してログを出力
```

### stop

```bash
docker-compose stop       # 全てのサービスを停止
docker-compose stop rails # サービスを指定して停止
```

### down

```bash
docker-compsoe down       # 全てのサービスを停止&削除
docker-compsoe down rail  # サービスを指定して停止&削除
```

### kill

```bash
docker-compsoe kill       # 全てのサービスを強制停止
docker-compose kill rails # サービスを指定して強制停止
```

## Config - `docker-compose.yml`

### 全体

| name     | description                                                                      |
| -------- | -------------------------------------------------------------------------------- |
| version  | 使用するバージョン。3 系が最新バージョン                                         |
| services | アプリを動かす要素。1 コンテナにつき、1 サービス。                               |
| volumes  | マウントするボリュームのパス（Host : Container）                                 |
| network  | デフォルトのアプリ用のネットワークを使う代わりに、自分で任意のネットワークを指定 |

### services

| name    | description                                      |
| ------- | ------------------------------------------------ |
| image   | イメージの名前                                   |
| build   | `Dockerfile`のあるディレクトリのパスを指定する。 |
| command | デフォルトのコマンドを上書きする。               |
| links   | 他のコンテナにリンクする。                       |
| ports   | 公開（EXPOSE）するポート。                       |
| volumes | マウントするボリュームのパス。                   |
