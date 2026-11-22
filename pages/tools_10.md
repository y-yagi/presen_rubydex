# SKILL(experimental)

* エージェント向けのスキル(`SKILL.md`)がgemに同梱されている
  * 現状は[`send-private-method`](https://github.com/Shopify/rubydex/blob/main/skills/send-private-method/SKILL.md)(`send`でprivateメソッドを呼んでいる箇所の直し方)のみ
* ルールが違反と一緒にスキルのIDを返し、エージェントは`rdx skill <id>`で取得する、という仕組みを想定している
  * ただし、v0.4.4時点ではスキルのIDを返すビルトインのルールはまだ無い
