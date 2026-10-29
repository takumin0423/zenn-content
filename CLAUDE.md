# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## リポジトリ概要

Zenn（zenn.dev）の記事・本をGitHub連携で管理するコンテンツリポジトリ。アプリケーションコードやビルド・テストはなく、中身はZenn CLI（`zenn-cli`）とMarkdownのみ。`main`へのpushがそのままZennへのデプロイになるため、`published: true` の記事の変更は即座に公開される点に注意する。

## AIの役割

文章は基本的に人間が書く。AIの役割は書かれた文章のレビューと、構成やネタ出しなどアイデアの壁打ち相手。

- 頼まれない限り、記事本文を書いたり書き換えたりしない。指摘や修正案は会話の中で示し、反映するかどうかは書き手が決める
- レビューでは技術的な正確さ、論理の流れ、読者にとっての分かりやすさ、誤字脱字を見る。文体を自分好みに寄せる指摘はしない
- 壁打ちでは、答えを出すよりも問いや選択肢を示して書き手の考えを引き出す

## コマンド

Node.jsとpnpmのバージョンは `mise.toml` で管理（`package.json` の `packageManager` とも一致させる）。

- `pnpm exec zenn preview` — ローカルプレビュー（http://localhost:8000）
- `pnpm exec zenn new:article --slug <slug> --title "<title>" --type tech|idea --emoji <emoji>` — 記事作成（引数省略時はslugがランダム生成される）
- `pnpm exec zenn new:book` — 本の作成
- `pnpm exec zenn list:articles` / `list:books` — 一覧表示

`pnpm test` はnpm initのデフォルトのままで意味を持たない。

## 構成

- `articles/<slug>.md` — 記事。ファイル名がslug（12〜50文字、`a-z0-9-_`）で、公開URLにも使われるため公開済み記事のリネームは不可
- `books/` — 本（現状は空）
- `images/` — 記事内画像。本文からは `/images/<file>` の絶対パスで参照し、ファイル名のスペース等はURLエンコードする（例: `/images/スクリーンショット%202025-11-14%2012.24.28.png`）

## 記事のフロントマター

```yaml
---
title: "..."
emoji: "📚"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["pnpm"]          # 最大5つ
published: true
publication_name: relic_tech  # 会社Publication（relic_tech）から出す記事のみ付与
---
```

## 既存記事の文体

レビューや修正案ではこの文体を前提にする（基準は既存記事 `articles/*.md`）。

- です・ます調。ただし**文末の「。」は付けず改行で区切る**スタイル
- 本文は `## はじめに` から始まり `## まとめ` で終わる構成が基本（h1はタイトルから自動生成されるため使わない）
- 参照URLはZennのリンクカード化のため単独行に置く
- Zenn独自記法（`:::message`、`:::details タイトル`、Mermaid、KaTeX）が使える
