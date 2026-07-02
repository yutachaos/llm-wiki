---
title: LLM Wiki パターン
type: topic
sources:
  - sources/karpathy-llm-wiki-gist.md
updated: 2026-07-02
---

# LLM Wiki パターン

[Andrej Karpathy](../entities/andrej-karpathy.md) が提唱した、LLM が構築・保守する個人ナレッジベースのパターン。出典: [LLM Wiki (karpathy gist)](../sources/karpathy-llm-wiki-gist.md)。

## RAG との対比

RAG は質問のたびにソースを検索して情報を再発見する。LLM Wiki は逆に、読解・統合の成果を wiki という**永続的で複利的な成果物**（persistent, compounding artifact）として蓄積し、以後はそれを一次知識源とする。相互参照や統合知が使うほど増えていく。

## 3層構造

1. **生ソース** — イミュータブルな入力文書。LLM は読むが変更しない
2. **wiki** — LLM が生成・保守する markdown ページ群
3. **スキーマ** — wiki の構造と運用ワークフローを定める設定文書（本リポジトリでは `CLAUDE.md`）

## 3操作

| 操作 | 内容 |
|---|---|
| Ingest | 新ソースを読み、要点を抽出して既存の複数ページ（10〜15 ページ規模）に横断的に統合する |
| Query | wiki を一次知識源として既存ページから回答を合成する |
| Lint | 矛盾・陳腐化・孤立ページ・相互参照漏れの定期健全性チェック |

## ナビゲーション

- `index.md` — カテゴリ別のコンテンツカタログ
- `log.md` — 追記型の時系列ログ（wiki の進化の記録）

## なぜ機能するか

ナレッジベース保守で退屈なのは読むことでも考えることでもなく**ブックキーピング**（索引付け・相互参照・整合性維持）であり、そこを LLM が肩代わりすることで、人手では停滞しがちなナレッジベースが複利的に成長する。
