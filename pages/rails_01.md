# Railsアプリケーションで使う

* Gemfileに追加するだけ

```ruby
group :development do
  gem "rubydex", require: false
end
```

* Bundlerの情報から依存gemもindexされるので、Railsのクラスとの継承関係も辿れる
  * `ApplicationRecord`から`ActiveRecord::Base`以降の祖先など
* アプリの起動(Railsの読み込み)は不要なので、DB接続などの準備もいらない
