# 構成

```text
rust/rubydex/      解析のコア(Rust)
rust/rubydex-sys/  C ABIでコアの機能を公開するFFI層(Rust)
ext/rubydex/       rubydex-sysを呼び出すRubyのC拡張
lib/rubydex/       Ruby側のAPI、CLI(rdx)、Linter、MCPサーバ
```

* Rubyのパースには[ruby-prism](https://crates.io/crates/ruby-prism)、RBSのパースには[ruby-rbs](https://crates.io/crates/ruby-rbs)のcrateを使用
  * ruby-prismは、Prism本体のリポジトリで元々提供されていたのを使用
  * ruby-rbsは2026年に公開された新しいcrate。RBSのリポジトリで、Rubydexのコントリビュータ(Alex Rocha)が追加した
