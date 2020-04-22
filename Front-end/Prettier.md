# Prettier

## Configuration

`.prettierrc`に記述します。

| option                    | default     | description                                          |
| ------------------------- | ----------- | ---------------------------------------------------- |
| printWidth                | 80          | 折り返す行の長さ                                     |
| tabWidth                  | 2           | タブ幅                                               |
| useTabs                   | false       | スペースではなくタブでインデントする                 |
| semi                      | true        | ステートメントの最後にセミコロンを記述する           |
| singleQuote               | false       | 二重引用符の代わりに単一引用符を使用する             |
| quoteProps                | "as-needed" | オブジェクトのプロパティに引用符を付けるか           |
| jsxSingleQuote            | false       | JSX で、二重引用符の代わりに単一引用符を使用する     |
| trailingComma             | "none"      | 複数行の場合、可能な鍵地末尾のコンマを記述する       |
| bracketSpacing            | true        | オブジェクトリテラルの各カッコの間にスペースを入れる |
| jsxBracketSameLine        | false       | JSX のブラケットを最後の行の末尾に置く               |
| arrowParens               | "avoid"     | アロー関数の引数をカッコで囲むか                     |
| rangeStart                | 0           |                                                      |
| rangeEnd                  | Infinity    |                                                      |
| parser                    | -           | 使用するパーサー                                     |
| filepath                  | -           | 使用するファイル                                     |
| requirePragma             | false       | プラグマが必要か                                     |
| insertPragma              | false       | プラグマを挿入するか                                 |
| proseWrap                 | "preserve"  |                                                      |
| htmlWhitespaceSensitivity | "css"       |                                                      |
| endOfLine                 | "auto"      | 行末                                                 |
