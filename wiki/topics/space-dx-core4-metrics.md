---
title: SPACE framework と DX Core 4
type: topic
sources:
  - sources/dx-core-4-space-framework.md
updated: 2026-08-20
---

# SPACE framework と DX Core 4

- 分野: 開発者生産性の測定
- 出典: [SPACE framework と DX Core 4](../sources/dx-core-4-space-framework.md)

## 概要

[DORAメトリクス（Four Keys）](dora-metrics.md)がデリバリーパフォーマンスに焦点を当てるのに対し、SPACE / DX Core 4 はより広く「開発者の生産性・体験」全体を測ろうとするフレームワーク群。

## 主要概念

### SPACE framework

開発者生産性を5次元で捉える:

| 次元 | 内容 |
|---|---|
| Satisfaction | 満足度 |
| Performance | パフォーマンス |
| Activity | 活動量 |
| Communication & collaboration | コミュニケーション・協働 |
| Efficiency & flow | 効率・フロー |

カテゴリを提示するのみで具体的な測定項目までは定義していないため、自前でメトリクスを設計する難易度が高く、多くのチームが1四半期以内に運用を放棄したとされる。

### DX Core 4

DORA・SPACE・DevExを統合した単一フレームワーク。4次元:

- **Speed**: PR数/エンジニア、リードタイム、デプロイ頻度
- **Effectiveness**: 開発者体験・フロー効率
- **Quality**: 本番の安定性・信頼性
- **Impact**: ビジネス価値への貢献度

「定義の統一」に加え、組織間ベンチマーク・チーム〜組織全体へのドリルダウン・インプットとアウトプット双方の可視化を狙う。

## マネジメントへの適用

- [DORAメトリクス](dora-metrics.md)だけでは「開発者体験」側が見えにくい。満足度やフローの停滞は別軸で測る必要がある
- SPACEをそのまま導入するとメトリクス設計で頓挫しやすい、という失敗パターンは、[Platform Engineering](platform-engineering.md)における「測定ギャップ」（約3割が成功指標を測定できていない）と同根の問題として捉えられる
- 指標を後付けでなく最初から定義しておく、という一貫した教訓がDORA・SPACE・DX Core 4・CNCF Platforms White Paperのいずれにも共通する

## 関連

- [DORAメトリクス（Four Keys）](dora-metrics.md)
- [Platform Engineering](platform-engineering.md)
- [ニコール・フォースグレン](../entities/nicole-forsgren.md) — DORA・SPACE 双方の共著者
- [OKR と目標管理（MBO）](okr.md) — 健康診断指標を目標に転用したときの歪みについて
