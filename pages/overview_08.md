# 背景(Ruby LSP)

* Ruby LSPの旧Indexer(`RubyIndexer`)は十分に速くなかったため、indexをスレッドで非同期に実行していた
  * その結果、race conditionの問題が起きていた
* Rubydexは速いので、同期的にindex出来るようになった
* Ruby LSPの`v0.27.0.beta`で、旧Indexerを削除してRubydexに移行している
  * [Migrate to Rubydex and remove old indexer #4103](https://github.com/Shopify/ruby-lsp/pull/4103)
