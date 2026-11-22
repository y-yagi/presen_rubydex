---
zoom: 0.85
---

# Ruby API

```ruby
user = graph["User"]

user.definitions.map { _1.location.to_file_path }
# => ["app/models/user.rb", "app/models/user2.rb"]

user.ancestors.map(&:name).first(6)
# => ["User", "Nameable", "ApplicationRecord", "ActiveRecord::Base",
#     "ActiveRecord::Marshalling::Methods", "ActiveRecord::Suppressor"]

user.member("display_name()")&.name   # => "User#display_name()"
user.find_member("initials()")&.name  # => "Nameable#initials()" (祖先から探す)
```

* gemのコードもindexされているので、`ActiveRecord::Base`以降のancestorsも辿れる
