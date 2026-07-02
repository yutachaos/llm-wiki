# llm-wiki

LLM（Claude Code）が構築・保守する個人ナレッジベース。
[karpathy の LLM Wiki パターン](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)の実装。

## 使い方

Claude Code でこのリポジトリを開き、以下のスキルを使う:

- `/ingest <ファイルパス or URL>` — ソースを取り込み、wiki に統合する
- `/query <質問>` — wiki を知識源として質問に答える
- `/lint` — wiki の健全性チェック（矛盾・リンク切れ・孤立ページ等）

## 構成

- [wiki/index.md](wiki/index.md) — ページカタログ（閲覧の起点）
- [wiki/log.md](wiki/log.md) — 操作ログ
- `sources/` — 生ソース（イミュータブル）
- `CLAUDE.md` — スキーマ（構造・運用ルール）
