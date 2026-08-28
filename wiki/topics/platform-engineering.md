---
title: Platform Engineering
type: topic
sources:
  - sources/platform-engineering-overview.md
  - sources/cncf-platforms-white-paper.md
  - sources/evan-bottcher-platforms-essay.md
  - sources/thoughtworks-radar-platform-teams.md
  - sources/backstage-adoption-guide.md
updated: 2026-08-20
---

# Platform Engineering

- 分野: ソフトウェアデリバリー・組織設計
- 出典: [Platform Engineering 概説（2026年時点）](../sources/platform-engineering-overview.md)、[CNCF Platforms White Paper](../sources/cncf-platforms-white-paper.md)、[What I Talk About When I Talk About Platforms](../sources/evan-bottcher-platforms-essay.md)、[ThoughtWorks Technology Radar](../sources/thoughtworks-radar-platform-teams.md)、[Backstage導入ガイド](../sources/backstage-adoption-guide.md)

## 概要

Internal Developer Platform（IDP）の設計・構築・運用を通じて、開発者がインフラを自前で組み立てずにセルフサービスでビルド・デプロイ・運用できるようにする規律。CNCF（TAG App Delivery）の定義では「プラットフォームの利用者のニーズに応じて定義・提供される、統合されたケイパビリティの集合」。DORA は「ソシオテクニカルな規律」と呼び、チーム間相互作用と自動化・セルフサービス・再現性という技術的な仕事の交差点に位置づける。

クラウドネイティブ化・Kubernetes・マイクロサービス化が進んだことで、DevOps の「you build it, you run it」が実質的に全プロダクトチームをインフラチーム化させ、認知負荷がボトルネックになった反動として生まれた。

## 矛盾

- platformengineering.com の記事は「a platform is an integrated product that abstracts away the underlying complexity of the technology stack」を CNCF Platforms Working Group の "canonical formulation" として引用しているが、CNCF Platforms White Paper の実際の定義文は "an integrated **collection of capabilities** defined and presented according to the needs of the platform's users" であり、引用が不正確（「複雑さの抽象化」ではなく「ケイパビリティの集合」が原文の骨子）。本ページの定義は CNCF White Paper 側の原文に基づく

## 主要概念

### IDP の構成要素

- **Golden paths**: サービス起動・環境デプロイ・シークレットローテーションなどの定型ワークフロー
- **セルフサービスインターフェース**: CLI・Webポータル・API
- **開発者ポータル**: Backstage が代表例
- **標準化されたビルディングブロック**: 再利用可能な IaC モジュール、コンテナテンプレート
- **組込みガバナンス**: policy-as-code、コンプライアンス自動化
- **可観測性・FinOps**: コスト可視化・ログ・メトリクス・トレースがデフォルト有効

### DevOps・SRE との位置づけ

DevOps は協働の文化・哲学、SRE は信頼性の規律（エラーバジェット、SLO）、platform engineering はそれらを golden path として具体化・製品化する配信層。「置き換え」ではなく三者の組み合わせが成熟パターンとされる。

### 「プラットフォームをプロダクトとして扱う」

成功しているプラットフォームチームに共通するのは、ロードマップ・専任PM・価値伝達・フィードバックループを持つプロダクトとしてIDPを運営すること。逆に mandate（トップダウン強制）主導の採用や、兼任・ボランティアベースの予算不足チームは失敗パターンとされる。

CNCF White Paper は、プラットフォームチームは通常 compute/network/storage などの裏側サービス自体は運用せず、マネージドプロバイダーやインフラチームに依存し、他に手段がない場合のみ独自ケイパビリティを構築すべきとする。認知負荷対策として「thinnest viable platform layer（最も薄い実行可能なプラットフォーム層）」を推奨しており、プラットフォームチーム自身が新たな認知負荷の発生源にならないことを重視している。

### 測定の課題

フロータイム・認知負荷・スループット・キャパシティ配分を測るべきとされる一方、2026年時点でも約3割の組織が成功指標を全く測定していない、という測定ギャップが指摘されている。CNCF White Paper は測定軸を「ユーザー満足度・生産性（アクティブユーザー数、NPS、SPACEフレームワーク）」「組織効率（リクエスト〜提供のレイテンシ等）」「プロダクト・機能デリバリー（DORAメトリクス）」の3系統に整理している。

### AIとの融合（2024-2026の転換点）

- platform engineering がAIのビジネス価値実現に不可欠と考える組織が86%、AIをplatformの将来にとって重要と答える組織が94%（Google Cloud調査）
- Gartner Hype Cycle 2026 で「Agent Experience（AX）」という新設計領域が登場。AIエージェントが消費するバックエンドを発見可能・機械可読にする発想
- platform team がAIゲートウェイ・モデルルーターのガバナンス層を担う方向に拡大している

### Un-Platform Problem とバックログカップリング（Evan Bottcher）

CNCF White Paperより早い2018年の時点で、Evan Bottcherは「デジタルプラットフォームとは、セルフサービスAPI・ツール・サービス・知識・サポートの基盤であり、魅力的な社内プロダクトとして組み立てられたもの」と定義していた。サイロ化したインフラチームが並存する「Un-Platform Problem」の失敗事例では、チーム横断の調整が必要な変更に数週間〜数ヶ月かかった。特に「他チームの関与が必要なタスクは所要時間が10〜12倍遅くなる」というバックログカップリングの弊害が指摘されている。

対策として、強制ではなくチームが自発的に選びたくなる魅力的なデフォルトを提供するNetflixの「paved road（舗装路）」という考え方が紹介されている。これは CNCF White Paper の「thinnest viable platform」やIDPの「golden paths」と同じ方向性の先行的な概念。

### 批判・失敗パターン（ThoughtWorks Technology Radar）

ThoughtWorksは「platform engineering product teams」（明確な顧客とプロダクトを持つプラットフォームチーム）自体は一貫して推奨（Adopt）している一方、「miscellaneous platform teams」という失敗パターンにHoldの評価を出している。既存チームを働き方を変えずに単に「プラットフォームチーム」と改名しただけ、あるいは明確な成果を持たないプロジェクトの寄せ集めを担当させられたチームは、過大な認知負荷と優先順位の不整合に苦しみ、「何でも屋」の受け皿に陥る。プラットフォームチームという肩書自体が成果を保証するわけではない、という警鐘。

### Backstageの実例

開発者ポータルの代表例である[Backstage](../entities/backstage.md)の導入実態を見ると、「無料OSS」のイメージに反して自前実装には年間$380K〜650Kかかり、3〜5名の専任エンジニア（フロントエンド経験者を含む）と経営層のスポンサーシップが要る。成功しているのは100%導入を狙わず80%カバレッジを目標に段階導入したケースで、経営層のスポンサーシップなしの「作れば使われる」的なボトムアップ導入は失敗しやすいとされる。「IDPをプロダクトとして扱う」という原則の具体的なコスト・失敗パターンを示す実例。

## 測定手法

[DORAメトリクス（Four Keys）](dora-metrics.md)がデリバリーパフォーマンスに焦点を当てるのに対し、[SPACE framework と DX Core 4](space-dx-core4-metrics.md)はより広く開発者の生産性・体験全体を測ろうとするフレームワーク。SPACEは5次元のカテゴリを提示するのみで具体的な測定項目を定義しないため運用が頓挫しやすく、DX Core 4はDORA・SPACE・DevExを統合した4次元（Speed, Effectiveness, Quality, Impact）で測定の実務性を補おうとしている。

## マネジメントへの適用

- [チームトポロジー](team-topologies.md)の「プラットフォームチーム」は認知負荷を下げる内部プロダクトという設計概念だったが、platform engineering はその実践を具体的な IDP・golden path・開発者ポータルというレベルまで下ろしたもの、と位置づけられる
- [DORAメトリクス（Four Keys）](dora-metrics.md)と同様、platform engineering も「測定できないと改善判断ができない」という同じ罠に陥りやすい。指標を先に決めてから展開するのが良さそう
- プラットフォームチームの評価を「使われているか（採用率・NPS）」で見る発想は、開発者を「顧客」として扱うプロダクト思考の応用
- 「プラットフォームチーム」というラベルを付けるだけでは何も変わらない。明確な顧客・プロダクト・成果を定義できないなら、名乗る前にそこを先に詰めた方が良さそう

## 関連

- [チームトポロジー](team-topologies.md)
- [DORAメトリクス（Four Keys）](dora-metrics.md)
- [SPACE framework と DX Core 4](space-dx-core4-metrics.md)
- [コンウェイの法則](conways-law.md)
- [Backstage](../entities/backstage.md)
- [CNCF（Cloud Native Computing Foundation）](../entities/cncf.md)
- [カミール・フルニエ](../entities/camille-fournier.md) — "Platform Engineering: A Guide for Technical, Product, and People Leaders" (2024) の共著者
- [SRE（SLO・エラーバジェット）](sre-slo-error-budget.md) — platform engineering が前提に置く「信頼性の規律」の中身
