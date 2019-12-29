# VSCode

VSCode とは、**Microssoft が開発したオープンソースのテキストエディタ**です。拡張機能が便利で、統合ターミナルが使えます。必要な言語だけ拡張機能で追加できるので、UI や機能も最低限で済みます。

- [Visual Studio Code のインストールと使い方](https://eng-entrance.com/texteditor-vscode)
- [VSCode + WSL](https://qiita.com/remin/items/b764036e95a13075ee98)

## Installation

[Visual Studio Code の公式サイト](https://code.visualstudio.com/)からダウンロードします。

## Shortcuts

- [Windows 版](https://qiita.com/TakahiRoyte/items/cdab6fca64da386a690b)
- [Mac 版](https://qiita.com/naru0504/items/99495c4482cd158ddca8)

## Extensions

### Utility

| Extensions               | Description                                            |
| ------------------------ | ------------------------------------------------------ |
| Japanese Language Pack   | 日本語化                                               |
| Better Comments          | TODO や FIXME など、コメントハイライトを細かく設定可能 |
| Bracket Pair Colorizer 2 | 括弧の対応を色付きで表示してくれる                     |
| GitLens                  | Git 機能の拡張                                         |
| Path Intellisense        | パスの入力を補完                                       |
| Prettier                 | コードのフォーマッター。多言語に対応                   |
| Setting Sync             | ユーザー設定や拡張機能の設定を複数 PC 間で同期可能に   |
| zenkaku                  | コード内の全角の空白を表示                             |

### Markdown

| Extensions                | Description                    |
| ------------------------- | ------------------------------ |
| Markdown Alii in One      | 機能拡張                       |
| Markdown Preview Enhanced | プレビューをカスタマイズ可能に |
| markdownlint              | リンター                       |

### Solidity

- **solidity**
  Solidity 言語対応。

## Tips

### ターミナルを WSL に変更する

setting.json

```JSON
"terminal.integrated.shell.windows": "C:/Windows/System32/wsl.exe"
```

### WSL で Git を使う

1. [WSLGit](https://github.com/andy-5/wslgit)のバイナリ`wslgit.exe`をダウンロードし、適当なディレクトリに移動。
2. パスを設定

   ```JSON
   // setting.json
   "git.path": "C:/bin/wslgit.exe"
   ```
