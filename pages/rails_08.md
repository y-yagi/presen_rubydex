# AIエージェントから使う

* `rdx mcp`をMCPサーバとして登録すると、Claude CodeやCodexなどからコードベースを検索出来る

```bash
claude mcp add --scope project rubydex -- bundle exec rdx mcp
```

* grepでは分かりにくい情報を正確に取れる
  * あるconcernをincludeしているモデルの一覧
  * 定数の参照箇所(同名の別の定数と区別される)
  * ancestorsやメンバーを含めたクラスの詳細
* MCPサーバは起動時にindexし、ファイルの変更は追跡しない
  * コードを変更したら、サーバの再起動が必要
