# Resolution

* 完全修飾名を計算してDeclarationを作る(`Foo::Bar`、`Foo#method()`、`Bar#@ivar`など)
* 定数の参照を解決する
* 祖先チェーンの線形化と、子孫の記録
* メソッドや定数がどのクラスに属するかの決定
* 暗黙のsingleton classの作成
* 実装は[`rust/rubydex/src/resolution.rs`](https://github.com/Shopify/rubydex/blob/main/rust/rubydex/src/resolution.rs)
