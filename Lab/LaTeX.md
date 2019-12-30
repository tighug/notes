# LaTeX

Tex とは、**フリーの組版システム**です。活版印刷のような「文字や図版などの要素を紙面に配置する」という作業をコンピュータで行うことができます。
LaTex とは、**Tex の上に構築されたフリーの文書処理システム**です。一般的な文書作成に便利なように拡張されています。

- [LaTex 入門 - TeX Wiki](https://texwiki.texjp.org/?LaTeX%E5%85%A5%E9%96%80)

## Installation

### 最小環境

エディタ「TeX Works」を[ここ](http://www.tug.org/texworks/#Getting_TeXworks)からダウンロード。Mac は「TeX Shop」の方が高機能で主流。長く使わない、エディタに特に拘りがない場合はこっち。

### フルパッケージ環境

フルパッケージ「TeX Live 2019」を[ここ](https://www.tug.org/texlive/acquire-netinstall.html)からダウンロード。「Tex Works」も中に含まれている。他エディタ（VSCode 等）と併用する場合はこっち。

#### インストール方法

- ISO イメージをマウント：速い
- ネットインストール：遅い（1 時間くらい）、自動

#### パッケージの削減

以下のパッケージは必要ない。

- ConTeXt パッケージ
- アフリカ文字
- ゲーム組版
- 日本語以外の言語（日中韓 (base)、英語、米語は外さない）
- Omega パッケージ
- 音楽パッケージ

## VSCode をエディタに使用する

## 使い方

## Tips

### 種類

日本語が使え、かつ主流なものを抜粋。

- **pLaTeX**
  LaTeX を日本語化したもの。昔は主流だった。学会などのテンプレートはこれが多い。「dvi」出力。
- **upLaTeX**
  pLaTeX を Unicode 化したもの。「dvi」出力。
- **pdfLaTeX**
  出力形式を「dvi」でなく「PDF」にしたもの。
- **XeLaTeX**
  フォントを自由に変更可能。「PDF」出力。
- **LuaLaTeX**
  pdfLaTeX に軽量スクリプト言語 Lua を組み込んだもの。高機能。少し遅い。
- **LuaJITLaTeX**
  pdfLaTeX に Lua ではなく LuaJIT を組み込んだもの。LuaLaTeX よりも軽量・高速化。

> LuaJIT：コンパイル方式の Lua 言語。インタプリタ方式の Lua よりも高速。
> （※ JIT（Just-In-Time Compiler））

### コマンド一覧

- [LaTeX - コマンド一覧](http://www1.kiy.jp/~yoka/LaTeX/latex.html)
- [LaTeX における数式の書き方（簡易版）](http://www.amy.hi-ho.ne.jp/kanada/latex/latexmath.html)
- [enumerate 環境の番号の記号の変え方メモ](http://tekitobibouroku.blog42.fc2.com/blog-entry-77.html)
- [eps は非推奨？](https://texwiki.texjp.org/?dvipdfmx%2F%E7%94%BB%E5%83%8F%E3%81%AE%E3%81%A8%E3%82%8A%E3%81%93%E3%81%BF)

## 早見表

### 数式

- 行内

  ```TeX
  $[数式]$
  ```

- 別行立て

  - 数式番号付き

    ```Tex
    \begin{equation}
    \end{equation}
    ```

  - 数式番号無し

    ```Tex
    \[
    \]
    ```

- 分数

  ```TeX
  \frac{分子}{分母}
  ```

- 括弧

  ```Tex
  \left(
  \right)
  ```

### 箇条書き

- 番号なし

  ```Tex
  \begin{itemize}
  \item ちゃお
  \item りぼん
  \item なかよし
  \end{itemize}
  ```

- 番号あり

  ```TeX
  \begin{enumerate}
  \item 富士
  \item 鷹
  \item なすび
  \end{enumerate}
  ```

### 目次

```TeX
\tableofcontents
```

### 図

```TeX
% プリアンブル
\usepackage[dvipdfmx]{graphicx}
```

```TeX
\begin{figure}
  \centering
  \includegraphics[width=幅]{ファイル名}
  \caption{説明}
\end{figure}
```

### 参照

| type     | label                | reference          |
| -------- | -------------------- | ------------------ |
| figure   | `\label{fig:[name]}` | `\ref{fig:[name]}` |
| table    | `\label{tab:[name]}` | `\ref{tab:[name]}` |
| equation | `\label{eq:[name]}`  | `\ref{eq:[name]}`  |
| section  | `\label{sec:[name]}` | `\ref{sec:[name]}` |

## ファイル

ビルドした際に出力されるファイルの説明。

- `.aux` 補助ファイル。「相互参照」機能を補助する。(※ auxiliary)
- `.log` ログファイル。
- `.dvi` 組版結果の dvi ファイル。

## コマンド

```bash
dvipdfmx [texFileName]
ptex2pdf [texFileName]
```
