# pr-review-simulation

外部メンテナーへの提出前に、コード変更を直接取り込める状態かレビューするエージェント用スキルです。
メンテナーを模したレビュアーが、コード・commit 構成・検証の証拠を突き合わせます。
PR 本文がある場合は、その記述も確認します。

対象は、外部メンテナーが採用・取り込みすることを想定した具体的な変更です。
取り込みを想定しない測定・診断用の branch や、自分自身が upstream オーナーであるリポジトリ内のレビューは対象外です。
手順と判断基準の正本は [SKILL.md](SKILL.md) です。

## 使い方

`SKILL.md` は Claude Code、Codex、opencode が共通して読める形式です。
各ツールのスキル探索先へ、このリポジトリを置くか symlink します。

```
~/.claude/skills/pr-review-simulation/SKILL.md
~/.codex/skills/pr-review-simulation/SKILL.md
~/.config/opencode/skills/pr-review-simulation/SKILL.md
```

実際のレビューでは [design-review](https://github.com/libratechw/design-review) を併用するため、こちらも配置してください。
変更そのものの設計は design-review、提出先の文脈で判断できるかは pr-review-simulation が扱います。
対象の base commit とコード差分、取り込み判断に必要な証拠を指定してレビューを依頼します。

レビュー結果は実在のメンテナーの判断を予測するものではありません。
重要な指摘はコードと証拠で確かめてから扱います。

## 貢献

手順の改善提案を歓迎します。判断を改善できる具体的な事例や根拠を添えてください。

## ライセンス

[CC0 1.0](LICENSE) で公開します。
