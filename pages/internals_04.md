# DefinitionとDeclaration

```ruby
# foo.rb
module Foo     # 1
  class Bar    # 2
  end
end

# other_foos.rb
class Foo::Bar # 3
end
class Foo::Bar # 4
end
```

* Indexingで4つのDefinitionが作られる
* Resolutionで`Foo`と`Foo::Bar`の2つのDeclarationにまとめられる
* Rubyはクラスを何度でも再オープン出来るので、この区別が必要
