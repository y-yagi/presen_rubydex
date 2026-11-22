---
zoom: 0.85
---

# 使われていないクラスを探す

* `rdx dead_code`で、参照されていないクラスやモジュールの候補が出せる
* ただ、Railsは規約で呼ばれるクラスが多いので、厳密なチェックは出来ない
* APIで絞り込んでどうにか

```ruby
app_dir = File.join(Dir.pwd, "app/")

graph.dead_code_candidates
  .reject { |d| d.name.end_with?("Controller", "Helper", "Job", "Mailer") }
  .select { |d| d.definitions.any? { _1.location.to_file_path.start_with?(app_dir) } }
  .each { puts _1.name }
```
