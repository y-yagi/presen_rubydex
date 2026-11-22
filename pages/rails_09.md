# 注意点

* Railsのメタプログラミングで定義されるメソッドは当然わからない
  * `has_many :posts`の`posts`、`scope`、`delegate`、DBのcolumnのattributeメソッドなど
  * `attr_accessor :draft`も`draft()`だけで、writerの`draft=()`はまだ取れない
    * 1つの定義から複数のメソッドができるケースを、今のモデルでは表現できていない
  * DSLの対応は[DSL handling #958](https://github.com/Shopify/rubydex/issues/958)で検討されている

---

# 注意点

* メソッドの参照はレシーバの型が分からないと解決できない
  * `@user.display_name`は`User#display_name()`の参照として記録されない
  * ローカル変数は現状未対応
