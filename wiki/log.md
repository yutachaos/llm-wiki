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
