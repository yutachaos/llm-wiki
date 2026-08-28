---
title: OKR と目標管理（MBO）
type: topic
updated: 2026-08-20
---

# OKR と目標管理（MBO）

- 提唱者: ピーター・ドラッカー（MBO）、アンディ・グローブ（Intel での iMBO）、ジョン・ドーア（Google への導入・普及）
- 分野: 目標設定・パフォーマンスマネジメント
- 出典: Drucker "The Practice of Management" (1954)、Grove "High Output Management" (1983)、Doerr "Measure What Matters" (2018)

## 概要

目標を組織で揃えるための仕組みの系譜。ドラッカーの MBO（Management by Objectives、目標による管理）を、アンディ・グローブが Intel で計測可能な形に作り替え（[High Output Management](high-output-management.md)）、ジョン・ドーアが 1999 年に Google へ持ち込んで OKR として広まった。「何を達成したいか（Objective）」と「達成をどう判定するか（Key Results）」を分離するのが構造上の核心。

## 主要概念

- **Objective**: 定性的で方向性を示す目標。記憶できる言葉であること
- **Key Results**: 達成度を判定する定量的な結果指標。1 Objective に 3〜5 個が目安。**やったこと（アウトプット）でなく起きた変化（アウトカム）**で書く
- **ストレッチ性**: 野心的な OKR は 100% 達成を前提としない（Google 流では 70% 前後が健全とされる）。全部達成できているなら目標が低い
- **報酬との分離**: 評価・賞与に直結させると達成可能な目標しか設定されなくなり、ストレッチ性が壊れる。OKR は方向づけの道具、評価は別プロセス
- **CFR**（Conversation / Feedback / Recognition）: ドーアが OKR の対になる実践として置いたもの。年次評価ではなく継続的な対話・フィードバック・承認で OKR を運用する
- **トップダウンとボトムアップの併用**: 全 OKR を上から降ろすとコミットメントが生まれない。上位 OKR に紐づく形で各層が自分の OKR を書く

## 矛盾

- 「Key Results はアウトカムで書く」という原則と、実務で計測可能なのはアウトプットしかないケースが頻繁に衝突する。ドーアはアウトカム重視を説くが、Grove 流の運用ではアウトプット指標（出荷数など）も許容されており、どこまで厳格に扱うかは組織による

## マネジメントへの適用

- KPI との違いを整理しておく。KPI は継続的に見る健康診断値、OKR は期間内に動かしたい変化。全 KPI を OKR にすると運用が破綻する
- OKR が「既にやる予定の作業リスト」になっていたら失敗のサイン。書き換えでなく、そもそも何を変えたいのかから議論し直す
- [DORAメトリクス](dora-metrics.md)や[SPACE / DX Core 4](space-dx-core4-metrics.md)は健康診断指標なので、OKR に組み込むと Goodhart の法則で歪む。目標化するなら「指標が悪化している原因の解消」を目標に置く
- ストレッチ目標と評価を分離できないなら、無理に Google 流を真似ず達成型（コミット型）の目標運用にした方が事故らない

## 関連

- [アンディ・グローブ](../entities/andy-grove.md)
- [High Output Management](high-output-management.md)
- [動機づけ理論](motivation-theory.md)
- [DORAメトリクス（Four Keys）](dora-metrics.md)
- [マネージャープレイブック: パフォーマンス管理](manager-playbook-performance.md)
