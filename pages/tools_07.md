---
zoom: 0.85
---

# カスタムルールのテスト

* `RuleTestCase`を使うと、期待する結果を`^^^^`で視覚的に書ける

```ruby
require "rubydex/linter/rule_test_case"

class ProhibitModelReopenTest < Rubydex::Linter::RuleTestCase
  def test_catches_model_reopens
    assert_diagnostics(
      "app/models/post.rb" => <<~RUBY,
        class Post < ActiveRecord::Base
              ^^^^ `Post` is defined more than once.
        end
      RUBY
      "app/models/other_post.rb" => <<~RUBY,
        class Post < ActiveRecord::Base
              ^^^^ `Post` is also defined here.
        end
      RUBY
    )
  end
end
```
