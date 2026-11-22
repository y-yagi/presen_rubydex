# 背景

* language server、型チェッカー、ドキュメント生成など、多くのツールがそれぞれ独自にRubyのコードをindexしている
  * Ruby LSP / Solargraph、Sorbet / Steep、RDoc / YARDなど
* パーサーがバラバラだった状況をPrismで統一したのと同じように、indexと静的解析の層も共通化したい、というのが動機
* Rubydex自体はツールではなく、ツールを作るための「エンジン」という位置付け
* 参考: [One engine, many tools — Introducing Rubydex](https://railsatscale.com/2026-05-12-one-engine-many-tools/)
