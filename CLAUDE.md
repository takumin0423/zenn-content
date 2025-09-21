# CLAUDE.md

このファイルは、Claude Code (claude.ai/code) がこのリポジトリで作業する際のガイドラインを提供します。

## リポジトリ概要

これは日本の技術知識共有プラットフォーム「Zenn」用のコンテンツ管理リポジトリです。Zenn CLIを使用して技術記事や本を執筆・管理します。

## よく使うコマンド

### コンテンツ管理
- `pnpm zenn preview` - 記事・本のローカルプレビューサーバーを起動
- `pnpm zenn new:article` - 新しい記事を作成（スラッグ自動生成）
- `pnpm zenn new:article --slug <slug> --title <title> --type <tech|idea> --emoji <emoji>` - 指定した設定で記事を作成
- `pnpm zenn new:book` - 新しい本を作成
- `pnpm zenn list:articles` - 記事一覧を表示
- `pnpm zenn list:books` - 本の一覧を表示

### 開発環境
- Node.js: 24.8.0（miseで管理）
- パッケージマネージャー: pnpm 10.17.0
- Zenn CLI: ^0.2.3

## ディレクトリ構成

- `articles/` - Zenn記事のMarkdownファイルを格納（例：`3404dc967e769d.md`）
- `books/` - Zenn本とそのチャプターを格納
- `mise.toml` - ツールバージョン管理設定（Node.jsとpnpmのバージョン）

## 記事フォーマット

記事はfrontmatterでメタデータを管理：
- `title`: 記事タイトル
- `emoji`: 記事のアイコン用絵文字（1文字）
- `type`: "tech"（技術記事）または "idea"（アイデア記事）
- `topics`: トピックタグの配列（最大5つ）
- `published`: 公開状態（true/false）

## 記事作成時の注意事項

### 日本語文章のチェックポイント
- 技術記事として適切な日本語を使用すること
- 「です・ます調」で統一すること
- 技術用語は適切にカタカナ表記またはアルファベット表記を使い分けること
- 句読点は「、」「。」を使用（「，」「．」は使わない）

### Markdownフォーマットの確認
- 見出しレベルは適切に階層化すること（h1は記事タイトルで自動生成されるため、本文はh2から開始）
- コードブロックには適切な言語指定を付けること（```typescript、```javascript など）
- リンクは正しく記述すること：`[リンクテキスト](URL)`
- 画像はZennの仕様に従って配置すること

### Zenn固有の記法
- メッセージボックス: `:::message`、`:::message alert`、`:::details`
- 数式: KaTeX記法をサポート（`$`または`$$`で囲む）
- ダイアグラム: Mermaid記法をサポート

## 重要事項

- 記事のスラッグは12〜50文字で、a-z、0-9、ハイフン、アンダースコアのみ使用
- すべてのパッケージ管理とZenn CLIコマンドは`pnpm`を使用
- トピックは最大5つまで設定可能
- 記事公開前に必ず`pnpm zenn preview`でプレビュー確認を行うこと