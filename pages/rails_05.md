---
zoom: 0.85
---

# アーキテクチャのルールをLinterで設定する

* カスタムルールで、アプリ独自の設計ルールを強制出来る
* 例: 「モデルからコントローラを参照してはいけない」

```ruby
# rubydex_linter/rules/models_must_not_reference_controllers.rb
module Rubydex::Linter::Rules
  # Models must not depend on controllers.
  class ModelsMustNotReferenceControllers < CustomRule
    def self.default_severity = Severity::Error

    def lint
      child_classes("ActionController::Base").each do |controller|
        controller.references.each do |ref|
          next unless ref.location.to_file_path.include?("/app/models/")

          add_diagnostic("Model references controller `#{controller.name}`.", ref.location)
        enIndexingとResolutiond
      end
    end
  end
end
```
