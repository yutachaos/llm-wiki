# llm-wiki スキーマ

LLM（Claude Code）が構築・保守する個人ナレッジベース。
[karpathy の LLM Wiki パターン](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)に基づく。
このファイルは wiki の「スキーマ層」であり、構造と運用ルールを定義する。スキーマの変更はユーザーの明示的な指示があるときのみ行う。

## 3層構造

| 層 | パス | 役割 |
|---|---|---|
| 生ソース | `sources/` | イミュータブルな入力文書。**追加のみ。編集・削除禁止** |
| wiki | `wiki/` | LLM が生成・保守する markdown ページ群 |
| スキーマ | `CLAUDE.md` | 本ファイル。構造と運用ルール |

## wiki の構成

- `wiki/index.md` — カテゴリ別カタログ。全ページへのリンク＋一行要約。ページの作成・削除時に必ず更新する
- `wiki/log.md` — 追記型の時系列操作ログ。**過去エントリの削除・書き換え禁止**
- `wiki/sources/<slug>.md` — ソース要約ページ（1 ソース = 1 ページ）
- `wiki/topics/<slug>.md` — トピック・概念ページ。複数ソースを横断する知識の統合先
- `wiki/entities/<slug>.md` — エンティティページ（人物・組織・ツール・プロダクト等）

## ページ規約

- ファイル名は kebab-case の英語スラッグ（例: `llm-wiki-pattern.md`）
- 本文は日本語で書く
- リンクは相対 markdown リンク（例: `[LLM Wiki パターン](../topics/llm-wiki-pattern.md)`）。GitHub 上でそのまま辿れる形式にする
- 各ページの先頭に frontmatter を付ける:

```markdown
---
title: ページタイトル
type: source | topic | entity
sources:
  - sources/xxx.md
updated: YYYY-MM-DD
---
```

## index.md の書式

カテゴリ（Sources / Topics / Entities）ごとの箇条書き:

```markdown
## Topics
- [LLM Wiki パターン](topics/llm-wiki-pattern.md) — LLM が永続的な wiki を保守する知識管理パターン
```

## log.md の書式

日付見出しの下に操作を追記:

```markdown
## 2026-07-02
- ingest: sources/llm-wiki-gist.md を取り込み。llm-wiki-pattern.md を新規作成、index 更新
```

## 運用ルール

- 知識の統合を優先する: 新規ページ作成は既存ページに収まらない場合のみ。まず既存の topic / entity への統合を検討する
- ページ間の相互リンクを積極的に張る（関連ページは双方向にリンク）
- ソース間・ページ間で矛盾がある場合は上書きせず、ページ内に「## 矛盾」セクションを設けて両論併記し、出典を明記する
- wiki を変更したら同一の作業内で `index.md` と `log.md` を更新する
- 3操作（ingest / query / lint）の手順は `.claude/skills/` の各 SKILL.md に従う
