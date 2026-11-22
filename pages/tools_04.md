# Linter

* `rdx lint`でLinterが実行出来る
* ビルトインのルールとして、解析の過程で分かる問題を報告出来るようになっている
  * `ParseError` / `ParseWarning`
  * `DynamicConstantReference`: `var::Foo`のような静的に解析できない定数参照
  * `DynamicAncestor`: 静的に解析できない`include`など
  * `InvalidMethodVisibility`、`UndefinedMethodVisibilityTarget`、など
