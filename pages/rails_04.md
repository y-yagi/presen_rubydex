---
zoom: 0.85
---

# コードベースの調査

* Cypherでモデルの一覧を出す

```bash
$ bundle exec rdx query "MATCH (c:Class)-[:HAS_ANCESTOR]->(:Class {name: 'ActiveRecord::Base'}) RETURN c.name"
c.name
-----------------
Post
Admin
User
ApplicationRecord
...
```

* concernをincludeしているクラス、あるクラスを参照しているファイル、なども出せる

```bash
$ bundle exec rdx query "MATCH (d:Document)-[:REFERENCES]->(:Class {name: 'User'}) RETURN d.uri"
```

* 初めて触るアプリの全体像を把握したい時に便利な気がする
