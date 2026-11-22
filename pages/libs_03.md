---
zoom: 0.85
---

# RuboCop

* 例えば`Lint/DuplicateMethods`は、別ファイルにある同名メソッドの重複を検出出来るようになる

```ruby
# a.rb
class Foo
  def bar; end
end

# b.rb
class Foo
  def bar; end # 別ファイルだけど重複として検出される
end
```

* 他にも`Lint/ConstantReassignment`、`Lint/MissingSuper`、`Style/Documentation`などがindexを参照する
* `Lint/ArgumentMismatch`(引数の数の不一致)、`Lint/UnusedPrivateMethod`、`Lint/DeprecatedReference`など、indexが前提の新しいCopもある
