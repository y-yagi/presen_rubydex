# ライブラリ作者にとって

* 「Rubyのコードを解析して、定義・継承関係・参照を知りたい」ツールの土台として使える
  * language server、linter、ドキュメント生成、コード検索、リファクタリングツール、など
* 自前でPrismのASTを辿って定数解決や祖先の計算を実装する必要がなくなる
  * Rubyの定数解決は割と複雑([docs/ruby-behaviors.md](https://github.com/Shopify/rubydex/blob/main/docs/ruby-behaviors.md)にまとまっている)
* `index_source`でディスクにないソースもindex出来るので、テストやエディタ連携もしやすい

```ruby
graph = Rubydex::Graph.new
graph.index_source("file:///foo.rb", "class Foo < Bar; end", "ruby")
graph.resolve
```
