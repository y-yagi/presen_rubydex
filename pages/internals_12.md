---
zoom: 0.85
---

# Ractor

* resolve済みの`Rubydex::Graph`は、コピーせずにRactor間で共有出来る

```ruby
graph = Rubydex::Graph.new
graph.index_workspace
graph.resolve
Ractor.make_shareable(graph)

ractor = Ractor.new(graph) { |g| g["Foo"]&.name }
ractor.value
```

* スレッドセーフティはRubyではなく、Rust側の`RwLock`で担保している
  * なので、`freeze`されたグラフでも`index_source`や`resolve`で更新出来る
  * 更新しながら他のRactorから読み込めるようになっている
