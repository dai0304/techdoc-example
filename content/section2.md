# Section 2 - 推奨プロジェクト構成

```
|
+- README.md      -- ドキュメントビルド方法等、リポジトリの設定
+- .circleci
|   +- config.yml -- Circle CI 設定
|
+- .gitignore     -- git 設定
+- .node-version  -- ndenv 設定 
+- book.json      -- Gitbook 設定
+- config         -- 校正ツール設定
|   +- ...
|
+- content
|   +- README.md  -- 文書本体の README
|   +- SUMMARY.md -- 目次等
|   +- ...        -- その他コンテンツ
|
+- _book          -- ビルド成果物
    +- ...
```
