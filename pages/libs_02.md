# RuboCop

* RuboCop 1.87で、Rubydexを使ったProject Indexの機能が追加された(experimental)
* 通常のCopはファイル単位でしか検査できないが、プロジェクト全体の情報を使って検査出来るようになる

```ruby
# Gemfile
gem "rubydex", require: false
```

```yaml
# .rubocop.yml
AllCops:
  UseProjectIndex: true
  ProjectIndexIncludesGems: true # gemのソースもindexする
```
