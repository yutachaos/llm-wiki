---
title: AI Fluency（4Dフレームワーク）
type: topic
sources:
  - sources/claude-academy-ai-fluency.md
updated: 2026-08-28
---

# AI Fluency（4Dフレームワーク）

- 提唱: Anthropic（Claude Academy「AI Fluency: Framework & Foundations」コース）
- 出典: [Claude Academy — AI Fluency](../sources/claude-academy-ai-fluency.md)

AI と「効果的・効率的・倫理的・安全」に協働するための能力体系。プロンプトの書き方という技術論を超えて、**任せ方・伝え方・評価・責任**の4能力として AI 活用を構造化する。

## AI との3つの関わり方

| 形態 | 内容 |
|---|---|
| Automation（自動化） | AI が指示に基づいて特定タスクを完了する |
| Augmentation（拡張） | 人間と AI が思考と実行のパートナーとして協働する |
| Agency（エージェンシー） | AI を独立して機能するよう設定し、知識と行動パターンを確立する |

4D フレームワークはこの3形態すべてに適用できる。

## 4つの能力

### Delegation（委任）— 何を任せるか

何を自分で行い、何を AI と協働し、何を AI に任せるかの戦略的決定。3要素: **Problem Awareness**（ゴールと必要な作業の把握）、**Platform Awareness**（AI の能力と限界の理解）、**Task Delegation**（人間と AI の強みに応じた作業分配）。目的は全自動化ではなく最適なパートナーシップの構築。

### Description（記述）— どう伝えるか

AI との明確なコミュニケーション。**Product**（成果物: 形式・読者・スタイル）、**Process**（アプローチ方法）、**Performance**（AI の振る舞い: 簡潔/詳細、挑戦的/支援的）の3観点で記述する。「AI は心を読めない」。

プロンプティングの6技法: コンテキスト提供 / 例示 / 制約の明確化 / タスクの段階的分解 / 思考時間の確保 / 役割・トーンの定義。改善プロンプトの作成を AI 自身に依頼するのも有効。

### Discernment（識別）— どう評価するか

AI の出力・過程・振る舞いの批判的評価。**Product**（出力の正確性・適切性）、**Process**（推論の妥当性・論理的誤謬）、**Performance**（協働スタイルの適合）の3観点。ドメイン知識が評価能力を高める — 人間の専門性は AI に置き換えられるのではなく評価側で効く。

### Diligence（誠実さ）— どう責任を持つか

他の3能力が効果性・効率性の軸なのに対し、倫理・セーフティの軸。**Creation**（システム選択とプライバシー・倫理の熟考）、**Transparency**（AI の役割の正直な開示）、**Deployment**（共有する出力の検証と結果責任）。

## Description-Discernment ループ

Describe → Discern → Refine → Integrate の反復サイクル。フィードバックで指示を調整し続け、**最終的な意思決定と統合は人間が担う**。単発のプロンプトでなくループとして AI 協働を設計する点が中核。

## マネジメント論との接続

- Delegation の構造は [High Output Management](high-output-management.md) の委譲論と同型: 委譲の度合いは相手（AI）の「タスク習熟度」= Platform Awareness で決め、委譲しても結果責任は残る（= Deployment Diligence）。モニタリング（抜き取り検査）は Discernment に対応する
- Automation → Augmentation → Agency の段階は、タスク習熟度に応じて「構造的指示 → 対話と支援 → 委譲と目標のみ」と関与を変えるグローブの枠組みの AI 版として読める
- ドメイン知識が Discernment を高めるという主張は、[LLM Wiki パターン](llm-wiki-pattern.md)のように人間側の知識を構造化して蓄積する営みが AI 活用の質に直結することを示唆する

## 関連

- [Claude Academy — AI Fluency](../sources/claude-academy-ai-fluency.md)
- [LLM Wiki パターン](llm-wiki-pattern.md)
- [High Output Management](high-output-management.md) — 委譲・タスク習熟度・モニタリングの枠組みとの同型性
