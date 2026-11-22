---
zoom: 0.85
---

# Cypherでのクエリ

```bash
$ bundle exec rdx query \
  "MATCH (m:Module {name: 'Nameable'})-[:HAS_DESCENDANT]->(c) RETURN c.name"
c.name
--------
Nameable
Admin
User

3 rows
```

* `--format json`でJSONでも出力出来る
* Rubyからも使える

```ruby
query = Rubydex::Query.parse("MATCH (c:Class) RETURN c.name")
result = query.run(graph)
result.rows.each { |row| puts row["c.name"] }
```
