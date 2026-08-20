---
title: Platform Engineering 概説（2026年時点）
type: source
sources:
  - sources/platform-engineering-overview.md
updated: 2026-08-20
---

# Platform Engineering 概説（2026年時点）

- 出典: [platformengineering.com の記事](../../sources/platform-engineering-overview.md)（2026年公開）

## 要点

### 定義

- Internal Developer Platform（IDP）の設計・構築・運用が中核。開発者がインフラを自分で組み立てずにビルド・デプロイ・運用できる、キュレーションされたセルフサービス層
- CNCF Platforms Working Group の定義: 「プラットフォームとは、技術スタックの背後にある複雑さを抽象化する統合されたプロダクトである」
- DORA はさらに踏み込み、platform engineering を「ソシオテクニカルな規律」と呼ぶ。チーム間の相互作用と、自動化・セルフサービス・再現性という技術的な仕事の交差点に位置する

### 生まれた背景

- クラウドネイティブ、Kubernetes、マイクロサービス、監視ツール、拡大するセキュリティ／コンプライアンス要件が、開発チームに持続不可能な運用負荷を強いた
- DevOps の "you build it, you run it" は文化的には強力だが、実践上は全プロダクトチームがインフラチーム化することを意味した
- WJAETS の分析: 「IDP単体で開発者の運用フォーカスを最大75%削減できる」

### IDP の構成要素

- **Golden paths**: サービス起動・環境デプロイ・シークレットローテーションなどの定型ワークフロー
- **セルフサービスインターフェース**: CLI・Webポータル・API
- **開発者ポータル**: Backstage が代表例。サービス・ドキュメント・オーナーシップ・テンプレートを一元化
- **標準化されたビルディングブロック**: 再利用可能な IaC モジュール、コンテナテンプレート、パイプライン雛形
- **組込みガバナンス**: policy-as-code、コンプライアンス自動化、シークレット管理
- **可観測性・FinOps**: コスト可視化・ログ・メトリクス・トレースがデフォルトで有効

### DevOps・SRE との関係

- DevOps = 協働の哲学・文化。Platform engineering = それを実現する具体的な「how」
- SRE = 信頼性の規律（エラーバジェット、SLO、インシデント対応）。platform team がこれを golden path に組み込む
- 「platform engineering が DevOps を置き換える」のではなく、DevOps文化 + SRE の厳密さ + platform engineering という製品化された配信層、の組み合わせが成熟パターン

### 最新の調査結果（2025-2026）

- DORA 2025: 90%の組織が IDP を使用、76%が専任プラットフォームチームを設置
- Google Cloud調査: 成熟した採用組織の71%が市場投入時間の顕著な加速を報告（未成熟組織は28%）
- 成熟度はまだ課題: Futurum Group調査では32%のみが運用段階、mastering段階は19%のみ
- 測定のギャップ: 29.6%がまだ成功指標を測定せず、24.2%は測定していても改善したか判断できない。「最適化・部門横断エコシステム」段階は13.1%のみ
- 市場規模: プラットフォームツール市場は2025-2030年でCAGR 21.9%、$8.68B成長予測

### AIとの融合（2024-2026の最大の転換点）

- CNCF/SlashData Q1 2026調査: 35%の組織がAIワークロード統合にハイブリッドアプローチ（既存プラットフォーム＋専用AIツール）を採用
- Google Cloud調査: 86%が「AIのビジネス価値実現にplatform engineeringが不可欠」と回答、94%が「AIはplatform engineeringの将来にとって重要」と回答
- Gartner Hype Cycle for Platform Engineering 2026 で新設計領域「Agent Experience（AX）」が登場。AIエージェントがユーザーとして消費するバックエンドを発見可能・機械可読にする設計思想
- AIゲートウェイや生成AIモデルルーターも、platform teamが担うガバナンス層として台頭

### 陥りやすい失敗

- mandate主導（トップダウン強制）の採用がまだ36.6%
- 兼任・ボランティアベースの予算不足チームが13.1%
- 前述の測定ギャップ
- 成功要因は「プラットフォームをプロダクトとして扱う」「golden pathsと開発者ポータルを提供する」「プロダクトマインドセットを適用する」ことに一貫して集約される（WJAETS）

### 2026年の「良い実践」のパターン

- IDPをロードマップ・専任PM・価値伝達・フィードバックループを持つプロダクトとして扱う
- CI/CDを繋ぎ合わせるだけでなく、統一された配信コントロールプレーンを構築する
- フロータイム・認知負荷・スループット・キャパシティ配分を測定する（虚栄指標ではなく）
- AIワークロードのガバナンス層としてプラットフォームを使う

## 関連ページ

- [Platform Engineering](../topics/platform-engineering.md)
- [チームトポロジー](../topics/team-topologies.md)
- [DORAメトリクス（Four Keys）](../topics/dora-metrics.md)
