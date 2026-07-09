- .venv はリポジトリ直下に存在しているはず
  - pythonを実行するときは.venvを使うこと
- データについては data.mdを参照すること
- プログラムを作成する際はsource_of_trurh.mdを参照すること
- コードを作成したり、編集するときは必ず入出力台帳を作成すること
- source_of_truth.mdに方針が書かれているので確認すること

構成例:
example/
  agent_docs/
    docs/
      source_of_truth.md     # 人間が編集する中心ファイル
      tool_registry_template.md      # プログラム台帳
      path_registry_template.md      # データ・モデル・出力先の台帳
      io.md                  # 入出力の書き方ルール
  scripts/
  src/
  configs/

tool_registry_template
path_registry_template
この二つは

tool_registry.yml
path_registry.yml
として作成してください
