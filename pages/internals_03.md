# グラフのモデル

* Document: ファイル(ディスクに保存されていないエディタ上の内容も含む)
* Definition: ソースコード上の1つの定義。見つけた内容をそのまま記録したもの
* Declaration: 同じ完全修飾名を持つDefinitionをまとめた、意味的な実体

```text
Declaration  完全修飾名ごとに1つ
    ↑↓       同じ完全修飾名の複数のDefinition → 1つのDeclaration
Definition   ソースコード上の1つの定義
    ↑↓       1つのDocument → その中にある複数のDefinition
Document     ファイル
```

* 上(Declaration)からでも下(Document)からでも辿れる
