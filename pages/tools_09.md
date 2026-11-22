---
zoom: 0.85
---

# MCPサーバ

* `rdx mcp`でMCPサーバとして起動出来る
* AIエージェントがコードベースを意味的に検索出来るようになる

```bash
claude mcp add --scope project rubydex -- bundle exec rdx mcp
```

| Tool | 内容 |
|------|------|
| `search_declarations` | クラス・モジュール・メソッド・定数のfuzzy search |
| `get_declaration` | ドキュメント・祖先・メンバーなどの詳細 |
| `get_descendants` | 継承・includeしているクラス/モジュール |
| `find_constant_references` | 解決済みの定数の参照箇所 |
| `find_dead_code_candidates` | dead codeの候補 |
| `get_file_declarations` | ファイル内の定義一覧 |
| `codebase_stats` | コードベースの統計 |
