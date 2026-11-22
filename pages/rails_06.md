---
zoom: 0.85
---

# アーキテクチャのルールをLinterで

```ruby
class Post < ApplicationRecord
  def url = UsersController.helpers.url_for(self)
end
```

```bash
$ bundle exec rdx lint
...
app/models/post.rb:4:13: error: ModelsMustNotReferenceControllers: Model references controller `UsersController`.

  def url = UsersController.helpers.url_for(self)
            ^^^^^^^^^^^^^^^
```

* 他にも
  * モデルの再オープンの禁止([公式ドキュメントの例](https://github.com/Shopify/rubydex/blob/main/docs/linter.md#creating-custom-rules))
  * 特定のディレクトリのクラスは特定の親クラスを継承すること
  * 特定の名前空間からの参照の禁止(Packwerkもどき)
