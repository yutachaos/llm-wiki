# Log

追記型の操作ログ。過去エントリは削除・書き換えしない。

## 2026-07-02
- init: リポジトリ構造・スキーマ（CLAUDE.md）・スキル（ingest / query / lint）を作成
- ingest: sources/karpathy-llm-wiki-gist.md を取り込み。wiki/sources/karpathy-llm-wiki-gist.md・wiki/topics/llm-wiki-pattern.md・wiki/entities/andrej-karpathy.md を新規作成、index 更新

## 2026-07-03
- add: マネジメント理論 12 トピックを新規作成（知識経営: seci-model / tacit-explicit-knowledge / ba / middle-up-down-management / wise-company-phronesis、スクラム・ソフトウェア開発: new-new-product-development-game / scrum / dora-metrics / conways-law / team-topologies、組織行動・人材開発: psychological-safety / adult-development-theory）。entities/nonaka-ikujiro.md を新規作成、index 更新。出典は各ページ冒頭に記載（ソースファイルなし、モデル知識由来）
- add: ローカル閲覧用ビューワー index.html を追加（wiki/index.md 起点、ビルド不要）。README に使い方を追記
- add: エンジニアのロールモデル 3 トピックを新規作成（engineering-career-ladder / engineering-manager / staff-engineer）、index 更新

## 2026-08-16
- ingest: https://basecamp.com/managers （37signals Manager Playbook、全16章）を取り込み。sources/basecamp-manager-playbook.md に保存。wiki/sources/basecamp-manager-playbook.md（要約）、wiki/entities/37signals.md、wiki/topics/manager-playbook-foundations.md、wiki/topics/manager-playbook-hiring-onboarding.md、wiki/topics/manager-playbook-performance.md、wiki/topics/manager-playbook-development.md を新規作成、index 更新。既存ページとの主題重複がなく矛盾もないため、統合先ではなく新規トピック群として作成
- lint: 多重レビューを実施。entities/37signals.md にソース外の無出典記述（創業者情報）を検出し修正
- revise: ユーザー要望によりsources/basecamp-manager-playbook.mdを日本語要約から原文（英語）に近い詳細な形で再取得・置き換え。再取得時に取得ツールが給与水準を「75th percentile」と誤生成（正しくは原文で "top 10%"）していたため、該当箇所をピンポイント再取得し修正。wiki側の要約ページは既に正しい記述だったため変更なし

## 2026-08-20
- add: WebSearchでピーター・ドラッカーの主要業績を調査（知識労働者、MBO、エグゼクティブの条件、自己探求、連邦分権制、体系的イノベーションの7つの機会）。entities/peter-drucker.mdおよびtopics/knowledge-worker.md・management-by-objectives.md・effective-executive.md・managing-oneself.md・federal-decentralization.md・sources-of-innovation.mdを新規作成。ソースファイルなし、web検索で事実確認したモデル知識由来（各ページに検証済みの出典URL明記）。既存の暗黙知と形式知ページに、野中による西洋経営学（ドラッカー含む）批判の文脈を追記し双方向リンク。team-topologies・middle-up-down-management・dora-metrics・engineering-career-ladder・manager-playbook-*の各ページにも関連リンクを追加、index更新
- ingest: https://platformengineering.com/features/what-is-platform-engineering-inside-the-discipline-reshaping-modern-software-delivery/ （platform engineeringの定義・背景・2025-2026年の調査データ・AIとの融合）を取り込み。sources/platform-engineering-overview.md に保存。wiki/sources/platform-engineering-overview.md（要約）、wiki/topics/platform-engineering.md を新規作成、index 更新。既存の team-topologies.md（プラットフォームチーム概念）・dora-metrics.md と双方向リンクを追加。矛盾なし
- lint: 別モデルにセカンドオピニオンを依頼し、platformengineering.com記事が引用するCNCF定義の誤り（"abstracts away complexity" は不正確、原文は "integrated collection of capabilities"）を検出。ingest: https://tag-app-delivery.cncf.io/whitepapers/platforms/ （CNCF Platforms White Paper）を追加取り込み。sources/cncf-platforms-white-paper.md に保存、wiki/sources/cncf-platforms-white-paper.md（要約）を新規作成。wiki/topics/platform-engineering.md の定義をCNCF原文に修正し「## 矛盾」セクションに誤引用の経緯を記載、thinnest viable platform・測定軸の3系統を追記。index 更新
- ingest: セカンドオピニオンで指摘された網羅性の不足を埋めるため4ソースを追加取り込み。(1) https://martinfowler.com/articles/talk-about-platforms.html （Evan Bottcher、Un-Platform Problem・バックログカップリング・paved road）、(2) ThoughtWorks Technology Radar の platform-engineering-product-teams（Adopt）・miscellaneous-platform-teams（Hold）ブリップ（批判的視点）、(3) https://earthly.dev/blog/backstage-adoption-guide/ （Backstage導入コスト・失敗パターンの実例）、(4) https://getdx.com/dx-core-4/ （SPACE framework・DX Core 4）。sources/ に4ファイル保存。wiki/sources/ に4要約ページ、wiki/entities/backstage.md、wiki/topics/space-dx-core4-metrics.md を新規作成。wiki/topics/platform-engineering.md に「批判・失敗パターン」「Backstageの実例」「測定手法」節を追加し、team-topologies.md・dora-metrics.md と双方向リンクを追加。矛盾なし
- lint: 多重レビュー（機械的チェック＋独立2エージェントによる事実検証・整合性チェック）を実施。(1) wiki/topics/platform-engineering.md・wiki/entities/backstage.md にあった「Spotify社内採用率99%/他社10%」という出典未確認の数値（検索結果スニペット由来で実際にingestしたBackstage導入ガイドの本文には存在しない）を検出し削除、(2) wiki/topics/conways-law.md からplatform-engineering.mdへの逆リンクの欠落を検出し追加。機械的チェック（リンク切れ・孤立ページ・幽霊エントリ・frontmatter・sources参照）は問題なし

## 2026-08-22
- add: WebSearchでOKR（Objectives and Key Results）を調査。アンディ・グローブがMBOを土台に開発した経緯、ジョン・ドーアがGoogleに伝えた経緯、Objective/Key Resultsの構造、MBOとの違い（コミット目標とアスピレーション目標の区別）を中心にtopics/okr.mdを新規作成。ソースファイルなし、web検索で事実確認したモデル知識由来（ページ冒頭に検証済みの出典URL明記）。既存のmanagement-by-objectives.md・manager-playbook-performance.mdと双方向リンクを追加、index更新。矛盾なし
