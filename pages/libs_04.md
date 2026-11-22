# Homebrew

* HomebrewはRubydexを使った独自のCopを作っている
  * [`Library/Homebrew/rubocops/single_use_method.rb`](https://github.com/Homebrew/brew/blob/main/Library/Homebrew/rubocops/single_use_method.rb)
  * 1回しか呼ばれていないメソッドを検出し、呼び出し元へのインライン化を促す
  * プロジェクト全体で、そのメソッド名の他の定義や参照がないことをindexで確認している
