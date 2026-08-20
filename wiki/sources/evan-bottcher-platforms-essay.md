---
title: What I Talk About When I Talk About Platforms（Evan Bottcher）
type: source
sources:
  - sources/evan-bottcher-platforms-essay.md
updated: 2026-08-20
---

# What I Talk About When I Talk About Platforms（Evan Bottcher）

- 出典: [martinfowler.com の記事](../../sources/evan-bottcher-platforms-essay.md)（2018-03-05）
- Team Topologies / CNCF が引く「thinnest viable platform」の源流となったエッセイ

## 要点

### 定義

「デジタルプラットフォームとは、セルフサービスAPI・ツール・サービス・知識・サポートの基盤であり、魅力的な社内プロダクトとして組み立てられたもの」。自律的なデリバリーチームが調整コストを減らして機能を素早くデプロイできるようにする。

### Un-Platform Problem（アンチパターン）

架空の金融サービス企業「BigCo」を例に、middleware・midrange・DBA・network等のサイロ化したインフラチームが別々の管理下で動くことの弊害を描く。チーム横断の調整が必要な変更は「数週間〜数ヶ月」かかり、エンジニアが必要な改善に着手すること自体を躊躇させた。

### バックログカップリング

プロダクトチームのバックログが他チームの作業キューに依存するとき、深刻な制約が生まれる。他チームの関与が必要なタスクは「所要時間が10〜12倍遅くなる」という調査が引用されている。この依存によるスローダウンは、当事者意識とモチベーションを毀損する。

### 良いプラットフォームの条件

- セルフサービスでプロビジョニング・設定・管理ができる
- 個別に使える discrete なサービスとして composable
- 硬直的な運用義務を課さず flexible
- ドキュメント・クイックスタートで easy to adopt
- デフォルトで secure and current

### 自律性 vs 標準化

「WebBiz」はチームに完全なインフラ自律性を与え、エンゲージメントと責任感を高めたが意思決定コストが増大した。対比としてNetflixの「paved road（舗装路）」概念を紹介: 強制ではなく、チームが自発的に選びたくなるような魅力的なデフォルトを提供する、という発想。

## 関連ページ

- [Platform Engineering](../topics/platform-engineering.md)
- [CNCF Platforms White Paper](cncf-platforms-white-paper.md)
- [チームトポロジー](../topics/team-topologies.md)
