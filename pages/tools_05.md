---
zoom: 0.85
---

# Linter

```bash
$ bundle exec rdx lint
Indexing workspace... finished in 155.35ms
Resolving graph... finished in 186.92ms
Linting...
Offenses:

app/models/report.rb:3:3: warning: ParseWarning: possibly useless use of :: in void context

  klass::Foo
  ^^^^^^^^^^

app/models/report.rb:3:3: information: DynamicConstantReference: Dynamic constant reference

  klass::Foo
  ^^^^^

3065 files inspected, 2 offenses detected: 0 errors, 1 warning, 1 info, 0 hints
```

* `rdx lint explain RuleName`でルールの説明が見れる
* Ruby LSP(beta)のアドオンも同梱されている
