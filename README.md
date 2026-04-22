# ユニティ AIチャットボット 運用メモ

株式会社ユニティの公式サポートチャットボットです。
オールマイト・てずくーる・ぷくっとシールLAB の3サービスに対応しています。

---

## 公開URL

https://ryo-claude.github.io/unity-chatbot/unity_chatbot_ai.html

---

## 構成

| 役割 | 内容 |
|------|------|
| フロントエンド | `unity_chatbot_ai.html`（このファイル1枚） |
| ホスティング | GitHub Pages（無料・帯域制限なし） |
| AIバックエンド | Google Apps Script（GAS）経由でClaude APIを呼び出し |
| ログ保存 | Googleスプレッドシートに自動記録 |
| メール送信 | GmailApp経由で担当者へ自動送信 |

---

## HTMLファイルの更新手順

1. デスクトップの `UnityBOT` フォルダ内の `unity_chatbot_ai.html` を編集
2. GitHubの unity-chatbot リポジトリを開く
3. `unity_chatbot_ai.html` をクリック → 右上の鉛筆アイコン → ファイルをアップロード
4. 「変更をコミットする」をクリック
5. 数分後に公開URLに反映される

---

## GASの更新手順

1. Google Apps Script を開く
2. 該当のプロジェクトを開いてコードを編集
3. 右上「デプロイ」→「既存のデプロイを管理」→ 鉛筆アイコン
4. バージョンを「新バージョン」に変更 →「デプロイ」をクリック
5. ※ URLは変わらないのでHTMLファイルの変更は不要

---

## APIキーの管理

- AnthropicのAPIキーは **GASのコード内にのみ記載**（HTMLファイルには含まない）
- キーの確認・再発行：https://console.anthropic.com
- キーが漏洩した場合はすぐにコンソールで無効化し、新しいキーを発行してGASに貼り直す

---

## 会話ログの確認

スプレッドシートで日時・質問・回答・セッションIDを確認できます。
同じセッションIDの行が同一ユーザーのやりとりです。
※ スプレッドシートのURLは社内管理資料を参照
