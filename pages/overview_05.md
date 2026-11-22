---
zoom: 0.85
---

# Ruby API

```ruby
require "rubydex"

graph = Rubydex::Graph.new
graph.index_workspace  # カレントディレクトリ + Gemfile.lockのgem + RBSをindex
graph.resolve          # 名前解決などを行い、グラフを完成させる

graph["User"]                  # 完全修飾名で取得
graph.search("#display_name")  # 名前で検索
graph.resolve_constant("Bar", ["Foo", "Baz::Qux"]) # ネストを考慮した定数解決

user = graph["User"]
user.definitions   # 定義されている箇所
user.ancestors
user.descendants
user.references    # 参照されている箇所
user.member("display_name()")
```
