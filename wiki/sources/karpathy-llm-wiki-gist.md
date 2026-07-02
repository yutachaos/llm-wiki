---
title: LLM Wiki (karpathy gist)
type: source
sources:
  - sources/karpathy-llm-wiki-gist.md
updated: 2026-07-02
---

# LLM Wiki (karpathy gist)

[Andrej Karpathy](../entities/andrej-karpathy.md) による gist。LLM を使った個人ナレッジベース構築パターン「[LLM Wiki パターン](../topics/llm-wiki-pattern.md)」を提唱する文書。本リポジトリの設計の原典。

## 要点

- RAG が毎回の質問でソースから情報を再発見するのに対し、このパターンは **LLM が永続的に保守する wiki** を構築する。"the wiki is a persistent, compounding artifact" — 相互参照と統合知が時間とともに蓄積・複利化する
- **3層構造**: ①生ソース（イミュータブル、LLM は読むだけ）②wiki（LLM が生成・保守する markdown）③スキーマ（構造とワークフローを定める設定文書）
- **3操作**:
  - Ingest — 新ソースを読み、既存の 10〜15 ページに横断的に統合する
  - Query — wiki を一次知識源とし、既存ページから回答を合成する（生ソースからの再導出はしない）
  - Lint — 矛盾・陳腐化・孤立ページ・相互参照漏れの定期健全性チェック
- **ナビゲーション**: `index.md`（カテゴリ別カタログ）と `log.md`（追記型の時系列ログ）
- 動機: "the tedious part of maintaining a knowledge base is not the reading or the thinking — it's the bookkeeping"。LLM がこのブックキーピングを肩代わりすることで、ナレッジベースが停滞せず複利的に成長する
