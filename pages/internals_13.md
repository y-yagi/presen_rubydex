# 構成

* RustでRuby拡張ライブラリを書く(最近の)デファクトである[rb-sys](https://github.com/oxidize-rb/rb-sys)と[magnus](https://github.com/matsadler/magnus)は使用していな
* Rubydexでも以前magnusが検討されていた
  * [Investigate how to set up a native extension using Rust #2](https://github.com/Shopify/rubydex/issues/2)
* ただ、Rubyのバージョンアップや、RubyのC APIの変更への追従に懸念があったとのこと
  * 外部の依存を増やして、メンテナンスの対象を増やしたくないって
  * [Investigate alternatives to Magnus for creating a Rust native extension #7](https://github.com/Shopify/rubydex/issues/7)

----

# 構成

* 結果、RustからC ABIを公開して、C拡張から手動でbindingする方式を採用した
* C ABIなので、Ruby以外の言語からも使える
  * 例: Rubyのランタイムに依存しないVS Codeの拡張
