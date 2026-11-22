---
zoom: 0.95
---

# Packwerk

* PackwerkのコアのパースやResolutionをRubydexに置き換えるPRが出ている
  * [Replace core parsing/resolution engine with Rubydex #447](https://github.com/Shopify/packwerk/pull/447)
* これまでは、Zeitwerkのパスの規約を元に`constant_resolver`で定数を解決していた
  * autoloadされるコードの定数しか解決できなかった
* Rubydexでは実際の定義を元に定数を解決するので、より多くの参照を解析出来る
  * Shopifyのモノリス(約6万ファイル)で、解決できる定数の参照が約3倍になったらしい
