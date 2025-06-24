## 🧩 ソリューション概要

このソリューションは、Microsoft 365 Copilotの **Meeting Insights API（パブリックプレビュー）** を活用し、Teams会議の議事録を自動取得・整形・表示するためのPower Platformソリューションです。

Power AutomateとPower Appsを組み合わせて、以下のような機能を提供します：

- Teams会議の議事録（Transcript）をGraph API経由で取得
- JSON形式の議事録をAI Builderで読みやすく整形
- Power Appsキャンバスアプリで議事録を表示・管理

---

## 📦 ソリューション構成

- Power Apps キャンバスアプリ
- Power Automate クラウドフロー
- AI Builder 

---

## 🚀 インポート方法

### PowerShellスクリプトで権限設定

1. [PowerShell 7以上をインストール](https://learn.microsoft.com/ja-jp/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.5)
2. `[ManagePermissionGrant.ps1](https://github.com/microsoft/PowerApps-Samples/tree/master/powershell/connectors/HTTPWithMicrosoftEntraId)` を実行
3. 対象クラウド環境とユーザー範囲（全ユーザー or 特定ユーザー）を選択

### GitHubのソリューションをインポートして利用

1. ソリューションをダウンロード
2. Power Apps 作成者ポータルにアクセス  
3. 「ソリューション」→「インポート」から `.zip` ファイルをアップロード  
4. フローを有効化し、ソリューションのカスタマイズをすべて公開

## 💼 必要なPower Platformライセンス

このソリューションを利用するには、以下のライセンスが必要です：

- **Power Apps Premium ライセンス**
- **AI Builder クレジット** （議事録の整形に使用）

詳細は以下のMicrosoft Learnをご参照ください：

- [Power Apps のライセンス オプション](https://learn.microsoft.com/ja-jp/power-platform/admin/powerapps-licensing)
- AI Builder のライセンスとクレジット

---

## 📎 注意事項

- 本ソリューションは **パブリックプレビュー中のAPI** を利用しています。将来的に仕様変更の可能性があります。
- PowerShellスクリプトの実行には管理者権限が必要です。

以上
