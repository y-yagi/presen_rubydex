# 速度

* `rails new --minimal`したアプリ(+モデル数個)で`index_workspace`した場合
  * 対象: 3,067ファイル(アプリ + Rails等のgem + RBSのcore/stdlib)
  * index: 約155ms、resolve: 約190ms
* gemを含まないアプリのコードだけなら、数十msで終わる
  * [basecamp/fizzy](https://github.com/basecamp/fizzy)の`app/`と`lib/`(363ファイル)で約20ms
* 筆者の環境(Linux x86-64)で、雑に計測した値
