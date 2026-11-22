---
zoom: 0.85
---

# IndexingとResolution


```ruby
# foo.rb
module Foo; end

# bar.rb
module Bar
  class Foo::Qux
  end
end
```

* `bar.rb`だけを見ても、`Foo::Qux`の`Foo`が何を指すのかは分からない
  * `Bar::Foo`かもしれないし、トップレベルの`Foo`かもしれない
* Rubyはファイルの読み込み順を静的に決められない(`autoload`、条件付きの`require`など)
* なので、Indexingではファイル単位で分かることだけを記録し、ファイルをまたいだ解釈は全ファイルのIndexing完了後に行う
* 詳細は[docs/architecture.md](https://github.com/Shopify/rubydex/blob/main/docs/architecture.md)参照
