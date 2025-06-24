## 🧩 ソリューション概要

このソリューションは、Microsoft 365 Copilotの **Meeting Insights API（パブリックプレビュー）** を活用し、Teams会議の議事録を自動取得・整形・表示するためのPower Platformソリューションです。

Power AutomateとPower Appsを組み合わせて、以下のような機能を提供します：

- Teams会議のCopilot で作成した議事録を Graph API 経由で取得
- Copilot が作成した議事録を AI Builder で指定のフォーマットに整形
- Power Appsキャンバスアプリで議事録を表示・管理
- モデル駆動型アプリでデータを一括管理

### アプリの利用イメージ
アプリは以下のように利用することができます。

アプリを開き、議事録を取得します。

取得した議事録はデフォルトあるいは指定したフォーマットで自動的に一括変換されます。

> [!Note]
> 議事録のフォーマットは、ユーザーごとに Dataverse に保存されます。

https://github.com/user-attachments/assets/82f6621a-b8d4-4aa1-ae5d-0afb7c89f6cc



---

## 📦 ソリューション構成

- **Power Apps キャンバスアプリ** : 自分の議事録を取得し、その議事録のフォーマットを編集する事ができます。
- **Power Apps モデル駆動型アプリ** : データの管理用に利用してください。
- **Dataverse テーブル** : フォーマットのテンプレートと取得した議事録を保存するテーブルを備えています。
- **Power Automate クラウドフロー** : Meeting Insights API から議事録を取得し、フォーマットに変換し、データを記録するクラウドフローです。
- **AI Builder** : Meeting Insights APIから取得した生の議事録データをキャンバスアプリで指定したフォーマットに変換するアプリです。

---

## 🚀 インポート方法

### PowerShellスクリプトで権限設定

1. [PowerShell 7以上をインストール](https://learn.microsoft.com/ja-jp/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.5)
2. ManagePermissionGrant.ps1 を[リポジトリからダウンロード](https://github.com/microsoft/PowerApps-Samples/tree/master/powershell/connectors/HTTPWithMicrosoftEntraId)してローカルでPowerShell 7以上のバージョンで実行
3. アクセス権限を設定 (こちらの詳細は、[私の Blog](https://www.geekfujiwara.com/tech/powerplatform/6984/)に記載しています)

### GitHubのソリューションをインポートして利用

1. [ソリューションをダウンロード](https://github.com/geekfujiwara/CopilotMeetingInsightsApp/releases)
2. Power Apps 作成者ポータルにアクセス  
3. 「ソリューション」→「インポート」から `.zip` ファイルをアップロード  
4. フローを有効化し、ソリューションのカスタマイズをすべて公開

> [!Note] 
> ソリューションのインポート時には以下のようにHTTP with Microsoft Entra ID で接続を作成するように促されることがあるかと思います。
>
> ![image](https://github.com/user-attachments/assets/757ab7f6-eb4a-4e98-a430-e8fbb04dfce5)
>
> その際は以下のように登録してください。
>
> 新しい接続を作成する
>
> ![image](https://github.com/user-attachments/assets/1aa7f2a5-f59d-47a0-9b17-b9a6338f32b8)
>
> `https://graph.microsoft.com` を共に入力し、サインインを行う
>
> ![image](https://github.com/user-attachments/assets/82c1ca66-a196-405a-a655-9291c5806438)
>
> このように接続できましたらOKです。
>
> ![image](https://github.com/user-attachments/assets/c12fe755-1ae1-4e8c-920e-49d618dc6431)
>
> もし、インポートのボタンが有効にならない場合は、一度戻り、「次へ」をおしてもう一度アクセスしてみてください。
>
> インポートボタンが有効化されているはずです。


## 💼 必要なPower Platformライセンス

このソリューションを利用するには、以下のライセンスが必要です：

- **Microsoft 365 Copilot ライセンス**
- **Power Apps Premium ライセンス**
- **AI Builder クレジット** （議事録の整形に使用）

---

## 📎 注意事項

- 本ソリューションは **パブリックプレビュー中のAPI** を利用しています。将来的に仕様変更の可能性があります。
- PowerShellスクリプトの実行には管理者権限が必要です。

以上
