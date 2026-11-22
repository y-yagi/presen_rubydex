# Name

* 定数の名前は、名前の文字列 + 親のスコープ + レキシカルなネスト、の組で表現される

```ruby
# Foo: Name(str: Foo, parent_scope: None, nesting: None)
module Foo
  # Bar: Name(str: Bar, parent_scope: None, nesting: Foo)
  # Qux: Name(str: Qux, parent_scope: Bar, nesting: Foo)
  class Bar::Qux
  end
end
```

* Resolutionでは、この3つの情報を使って定数が何を指しているかを決める
* 参照(Reference)はファイル + オフセットごとに作られ、Nameはスコープ構造ごとに一意になる
