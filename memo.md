# この資料について(記載時点の記録)

Rubydexは随時更新されているため、本資料がどの時点・どこまでの内容を元にしているかをここに記録する。

## 参照したソース

- リポジトリ: https://github.com/Shopify/rubydex
- 参照コミット: `3135280fc4648f1f15a1b3f1d2e3908d45b74c2d`
  - コミット日時: 2026-11-05 20:02:09 +0000
  - メッセージ: `Merge pull request #1098 from Shopify/dependabot/github_actions/ruby/setup-ruby-1.336.0`
- 動作確認したgemのバージョン: `rubydex 0.4.4`(2026-10-28リリース)
  - mainのREADMEにある`Location#path`は0.4.4には無い(`to_file_path`を使用)
- 資料作成日: 2026-11-22

## 関連

- Ruby LSP: `v0.27.0.beta1`(2026-04-01)からRubydexを使い始め、`v0.27.0.beta5`(2026-08-21)で旧インデクサを削除
  - https://github.com/Shopify/ruby-lsp/pull/4103
- RuboCop: 1.87でProject Index(`AllCops/UseProjectIndex`)を追加(experimental)
  - https://github.com/rubocop/rubocop/blob/master/docs/modules/ROOT/pages/usage/project_index.adoc
- Homebrew: `Library/Homebrew/rubocops/single_use_method.rb`でRubydexを使用

## 動作確認の環境

- `rails new demo --minimal`(Rails 8.1)に`User`/`Post`/`Admin`/`Nameable`/`UsersController`/`Report`を追加したアプリ
- 速度はLinux x86-64で雑に計測(index約155ms、resolve約190ms、3,067ファイル)
- basecamp/fizzy(`ab5283441`)の`app/`と`lib/`のみをindexして約20ms(363ファイル)

## Railsで確認した制約

- `has_many`などのDSLで定義されるメソッドはグラフに存在しない(`User#posts()`は`nil`)
- `@user.display_name`のような、レシーバの型が分からないメソッド呼び出しは参照として解決されない
- `dead_code`は定数のみが対象。コントローラなど規約で呼ばれるクラスも候補に出る
- カスタムルールは`self.default_severity`を定義しないと`NotImplementedError`になる
