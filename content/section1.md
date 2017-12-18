# Section 1 - Docker Image

この環境は `dai0304/docker-techdoc-ja` という Docker イメージを実体とします。
このイメージは次の機能を利用できます。

- [gitbook-cli](https://github.com/GitbookIO/gitbook-cli) によるドキュメントのビルド
    - HTML 成果物の出力ができます。
    - PDF 成果物の出力ができます。日本語フォントの埋め込みにも対応しています。
    - 文書内部で [PlanyUML](http://plantuml.com/) による作図ができます。
- 文書校正
    - [textlint](https://textlint.github.io/) による文書チェックができます。
    - [RedPen](http://redpen.cc/) による文書チェックができます。
- 成果物のデプロイ
    - [AWS CLI](https://aws.amazon.com/jp/cli/) を使った S3 へのデプロイができます。

## ドキュメントの記述

Gitbook によるオーサリング環境です。Markdown で記述してください。

### コードハイライト

```json
[
  {
    "title": "apples",
    "count": [12000, 20000],
    "description": {"text": "...", "sensitive": false}
  },
  {
    "title": "oranges",
    "count": [17500, null],
    "description": {"text": "...", "sensitive": false}
  }
]
```

### PlantUML による作図

```uml
@startuml
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

Alice -> Bob: Another authentication Request
Alice <-- Bob: another authentication Response
@enduml
```

## 校正

エラーの指摘例は次のとおりです。

```
/root/workspace/content/section1.md
  14:52  ✓ error  原則として、全角文字と半角文字の間にスペースを入れます。                      preset-ja-spacing/ja-space-between-half-and-full-width
  14:54  ✓ error  原則として、全角文字と半角文字の間にスペースを入れます。                      preset-ja-spacing/ja-space-between-half-and-full-width
  51:21  error    本文を敬体(ですます調)に統一して下さい。
本文の文体は、敬体(ですます調)あるいは常体(である調)のどちらかで統一します。
"である。"が常体(である調)です。  preset-jtf-style/1.1.1.本文
  53:1   error    Found empty section: `## デプロイ`                                            no-empty-section
```

## デプロイ

Circle CI による成果物のデプロイができます。
