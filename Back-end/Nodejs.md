# Nodejs

Nodejs とは、**JavaScript をサーバーサイドで使えるようにしたもの**です。

- [npm 入門（Qiita）](https://qiita.com/maitake9116/items/7825d90c09f3e2f87dea)

## Installation

### Mac

「nodebrew」をインストール

```bash
brew install nodebrew
```

Nodejs をインストール。同時に NPM もインストールされる

```bash
nodebrew install-binary latest
```

使用するバージョンの指定

```bash
nodebrew use v7.1.0
```

### Linux

```bash
sudo apt purge nodejs
sudo apt autoremove
curl -L git.io/nodebrew | perl - setup
```

`~/.bashrc`に以下を記述して、パスを通す

```bash
export PATH=$HOME/.nodebrew/current/bin:$PATH
```

`.bashrc`を読み直す

```bash
source ~/.bashrc
```

#### nodejs のアップデート

```bash
nodebrew ls
nodebrew install-binary latest
nodebrew use latest
```
