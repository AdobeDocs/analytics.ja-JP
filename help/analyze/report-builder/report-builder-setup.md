---
title: Report Builderの設定
description: Adobe AnalyticsでReport Builderを設定する方法について説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: c3fe537967473754a3b5fe88c7b383647b2c742e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 67%

---

# Report Builder の設定

この記事では、Microsoft Excel でReport Builder for Adobe Analyticsを使用するための要件の概要を説明します。 アドインのインストール方法とセットアップ方法について説明します。

## 要件

Adobe AnalyticsのReport Builderは、次のオペレーティングシステムおよび web ブラウザーでサポートされています。

### macOS

- macOS バージョン 10.x 以降
- すべてのMicrosoft Excel バージョン

### Windows

- Windows 10、バージョン 1904 以降
- Excel バージョン 2106 以降

  すべての Windows デスクトップ Excel ユーザーは、アドインを使用するために Microsoft Edge Webview2 をインストールする必要があります。コントローラーをインストールするには：

   1. <https://aka.ms/webview2installer> にアクセスします。
   1. Evergreen スタンドアロンインストーラーを選択してダウンロードします。
   1. インストールプロンプトに従います。

### Web Office

- すべてのブラウザーとバージョンをサポート


## Report Builder Excel アドイン

Report Builder for Adobe Analyticsを使用するには、Report Builder Excel アドインをインストールする必要があります。 Report Builder Excel アドインをインストールすると、開いている Excel ワークブック内から Report Builder にアクセスできます。

### Report Builder アドインのダウンロードとインストール

Report Builder アドインをダウンロードしてインストールするには

1. Excel を起動し、新しいワークブックを開きます。

1. **[!UICONTROL 挿入]**/**[!UICONTROL アドインの取得]** を選択します。

1. Office アドインダイアログで、「ストア」タブを選択します。

1. 「Report Builder」を検索し、「追加 **[!UICONTROL をクリックし]** す。

1. ライセンス条項とプライバシーポリシーのダイアログボックスで、「**[!UICONTROL 続行]**」をクリックします。

**「ストア」タブが表示されない場合**

1. Excel で、ファイル／アカウント／設定を管理を選択します。

1. 「オプションの接続されたエクスペリエンスを有効にする」の横のボックスをオンにします。

1. Excel を再起動します。

**組織が Microsoft ストアへのアクセスをブロックしている場合**

IT またはセキュリティチームに連絡して、Report Builder アドインの承認をリクエストします。承認されたら、Office アドインダイアログで、「管理者による管理」タブを選択します。

![Office アドインダイアログの「管理者による管理」タブ ](./assets/image1.png)

Report Builder アドインをインストールすると、Report Builder アイコンが Excel の「ホーム」タブのリボンに表示されます。Excel リボンの「ホーム」タブに「Report Builder」アイコンが表示されます。

![Excel の「Report Builder」アイコン ](./assets/rb_app_icon.png)

## Report Builder へのログイン

使用しているプラットフォームまたはブラウザーに Report Builder for Excel アドインをインストールした後、次の手順に従って Report Builder にログインします。

1. Excel ワークブックを開きます。

1. Report Builder アイコンをクリックして、Report Builder を起動します。

1. Adobe Report Builder ツールバーで、「**[!UICONTROL ログイン]**」をクリックします。

   ![ 「Report Builderへのログイン」ボタンをクリックします。](./assets/rb_login.png)

1. Adobe Experience ID アカウント情報を入力します。アカウント情報は、Adobe Analyticsの資格情報と一致する必要があります。

   ![ ログインアイコンと組織。](./assets/image4.png)

ログインすると、パネルの上部にログインアイコンと組織が表示されます

## 組織の切り替え

最初のログインでは、プロファイルに割り当てられたデフォルトの組織にログインすることになります。

1. ログイン時に表示された組織の名前をクリックします。

1. 使用可能な組織のリストから組織を選択します。自身がアクセス権を持っている組織のみが表示されます。

   ![ アクセスできる組織のリスト ](./assets/image5.png)

## ログアウト

ユーザープロファイルで Report Builder からログアウトできます。

1. 開いているワークブックに加えた変更を保存します。

1. アバターアイコンをクリックして、ユーザープロファイルを表示します。

   ![ ユーザープロファイルのアバターと「ログアウト」ボタン ](./assets/image6.png)

1. 「**ログアウト**」をクリックします。
