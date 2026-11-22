# indexの対象

* `index_workspace`では、下記がindex対象になる
  * ワークスペース直下のファイルとディレクトリ(`.rb`、`.rake`、`.rbs`、`.ru`)
  * `Bundler.locked_gems`から取得した依存gemの`require_paths`
  * インストールされている最新の`rbs` gemの`core`と`stdlib`
    * `Integer`や`Array`などの組み込みクラスの情報はRBSから取得

----

# indexの対象

* 対象はRubyとRBSのファイルのみで、C拡張(`.c`)は解析されない
  * C拡張でのみ定義されているメソッド(例: Nokogiriの`Nokogiri::XML::Document#root`)はグラフに出てこない
  * 組み込みクラスやstdlibのC実装部分は、RBSで補われている
