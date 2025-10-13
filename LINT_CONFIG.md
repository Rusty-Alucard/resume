# Lint設定について

このプロジェクトはGitHub Pagesで公開される職務経歴書です。

## 設定ファイル

### markdownlint (.markdownlint.json)
GitHub Pages/Jekyll向けに最適化されたMarkdownlintの設定：

- **MD013**: 行の長さ制限を無効化（URLやバッジが長いため）
- **MD033**: HTML要素を許可（`<p>`, `<img>`などバッジ表示に必要）
- **MD041**: 最初の行が見出しでない場合を許可
- **MD024**: 重複見出しを兄弟要素のみチェック（職務経歴書の構造上必要）
- **MD001**: 見出しレベルの飛びを許可
- **MD026**: 見出しの末尾の句読点を許可
- **MD034**: Bare URLを許可

### textlint (.textlintrc)
日本語の技術文書向けの設定：

- **filters**: URLやmailtoリンクを除外
- **preset-ja-spacing**: 日本語のスペーシングルール
- **preset-ja-technical-writing**: 技術文書向けルール
- **preset-ai-writing**: AI生成コンテンツの検出

## 使用方法

```bash
# すべてのlintを実行
npm run lint:all

# textlintのみ実行
npm run lint

# markdownlintのみ実行
npm run lint:md

# textlintの自動修正
npm run lint:fix

# GitHub Pages向けlint（lint:allのエイリアス）
npm run lint:pages
```

## CircleCI連携

`.circleci/config.yml`でCIパイプラインに統合されています。
PRを作成すると自動的にlintチェックが実行されます。

