# Cypherでのクエリ

* グラフに対して、[Cypher](https://opencypher.org/)のサブセットでクエリが書ける
  * `MATCH`、`WHERE`、`RETURN`など読み込み用の句のみ対応
* ノード: `Document`、`Definition`、`Declaration`、`Class`、`Module`、`Method`、`Constant`など
* リレーション: `DEFINES`、`DECLARES`、`HAS_PARENT`、`INCLUDES`、`HAS_ANCESTOR`、`HAS_DESCENDANT`、`OWNS`、`REFERENCES`など
  * `rdx query --schema`で一覧が見れる
