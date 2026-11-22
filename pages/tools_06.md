# カスタムルール

* 独自のルールが書ける
  * `Rubydex::Linter::CustomRule`を継承して、`lint`メソッドを定義する
  * ルールは解析済みのグラフにアクセス出来る
* 下記のパスに置くと自動で読み込まれる
  * プロジェクト: `rubydex_linter/rules/**/*`
  * gem: `lib/rubydex_linter/rules/**/*`
* gemとしてルールを配布することも出来る
* 自動修正には未対応
