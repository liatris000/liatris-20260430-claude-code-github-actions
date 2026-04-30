# Claude Code × GitHub Actions — Issue→PR自動化テンプレート

GitHub IssueにClaude Codeを連携し、タスクを書くだけでブランチ作成・実装・PR作成まで自動化するテンプレートです。

## 機能

| トリガー | 動作 |
|---------|------|
| Issueに `claude` ラベル付与 | Claude Codeが実装してPRを作成 |
| Issue本文に `/claude-implement` | 同上 |
| PRコメントに `@claude review` | コードレビューを自動実行 |
| PRコメントに `@claude fix` | レビュー指摘を自動修正 |

## セットアップ

1. このリポジトリをフォーク or テンプレートとして使用
2. **Settings → Secrets and variables → Actions** を開く
3. `ANTHROPIC_API_KEY` を登録（Anthropicコンソールで取得）
4. Issueを作成して `claude` ラベルを付けて試す

## ワークフローファイル

```
.github/workflows/claude-issue-to-pr.yml
```

## 使い方

### Issue → PR 自動実装

1. Issueを作成（実装してほしい内容を詳しく書く）
2. `claude` ラベルを付ける
3. しばらくするとClaude Codeがブランチ `claude/issue-{番号}` を作成してPRを開く

### PR 自動レビュー

PRのコメント欄に以下を書くだけ:

```
@claude review
```

### レビュー指摘の自動修正

レビュー後に以下を書くだけ:

```
@claude fix
```

## 参考

- [Claude Code GitHub Actions ドキュメント](https://docs.anthropic.com/ja/docs/claude-code/github-actions)
- [Anthropic API キー取得](https://console.anthropic.com/)
