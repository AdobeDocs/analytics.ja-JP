---
title: Report Builderの設定
description: Adobe Analytics Report Builder for Excelのインストールと設定に関する詳細なガイドを説明します。 シームレスな統合のための設定手順を段階ごとに説明します。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: 1e893ce94ee3da46bbf22d7a90573681950d1135
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 39%

---

# Report Builderの設定

この記事では、[!DNL Microsoft] [!DNL Excel] でReport Builder for Adobe Analyticsを使用するための要件の概要を説明します。 アドインのインストール方法とセットアップ方法について説明します。

## 要件

Adobe AnalyticsのReport Builderは、次のオペレーティングシステムおよび web ブラウザーでサポートされています。

### macOS

- macOS バージョン 10.x 以降
- すべての [!DNL Microsoft] [!DNL Excel] バージョン

### Windows

- Windows 10、バージョン 1904 以降
- [!DNL Excel] バージョン 2106 以降

  すべての Windows デスクトップ [!DNL Excel] ユーザーは、アドインを使用するためにMicrosoft Edge Webview2 をインストールする必要があります。 コントローラーをインストールするには：

   1. <https://aka.ms/webview2installer> にアクセスします。
   1. Evergreen スタンドアロンインストーラーを選択してダウンロードします。
   1. インストールプロンプトに従います。

### Web Office

- すべてのブラウザーとバージョンをサポート


## Report Builder Excel アドイン

[!DNL Excel] for Adobe Analyticsを使用するには、Report Builder [!DNL Report Builder] アドインをインストールする必要があります。 Report Builder [!DNL Excel] アドインをインストールすると、開いている [!DNL Excel] ワークブック内からReport Builderにアクセスできます。

### Report Builder アドインのダウンロードとインストール

Report Builder アドインをダウンロードしてインストールするには

1. [!DNL Excel] を起動し、新しいワークブックを開きます。

1. **[!UICONTROL 挿入]**/**[!UICONTROL アドインの取得]** を選択します。

1. Office アドインダイアログで、「ストア」タブを選択します。

1. 「Report Builder」を検索し、「追加 **[!UICONTROL をクリックし]** す。

1. ライセンス条項とプライバシーポリシーのダイアログボックスで、「**[!UICONTROL 続行]**」をクリックします。

**「ストア」タブが表示されない場合**

1. [!DNL Excel] で、ファイル/アカウント/設定を管理を選択します。

1. 「オプションの接続されたエクスペリエンスを有効にする」の横のボックスをオンにします。

1. [!DNL Excel] を再起動します。

**組織が Microsoft ストアへのアクセスをブロックしている場合**

- IT またはセキュリティチームに連絡して、Report Builder アドインの承認をリクエストします。承認されたら、Office アドインダイアログで、「**[!UICONTROL 管理者による管理]**」タブを選択します。

  ![Office アドインダイアログの「管理者による管理」タブ &#x200B;](./assets/image1.png)

- または、[&#x200B; マニフェストファイル &#x200B;](https://reportbuilder.an.adobe.com/manifest.xml) を手動で取得し、独自の IT インフラストラクチャでファイルをホストすることもできます。 <br/>Microsoft Store から提供されない Excel マニフェストファイルをインストールする手順については、Microsoft Office [&#x200B; オンラインドキュメント &#x200B;](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish) に従ってください。

Report Builder アドインをインストールすると、[!DNL Excel] のリボンの「ホーム」タブに「Report Builder」アイコンが表示されます。

![Excel の「Report Builder」アイコン &#x200B;](/help/analyze/report-builder/assets/rb_app_icon.png)

## Report Builder へのログイン

使用しているプラットフォームまたはブラウザーにReport Builder for Excel アドインをインストールしたら、次の手順に従ってReport Builderにログインします。

1. Excel ワークブックを開きます。

1. Report Builder アイコンをクリックして、Report Builder を起動します。

1. Adobe Report Builderのツールバーで、「**[!UICONTROL ログイン]**」をクリックします。

   ![&#x200B; 「Report Builderへのログイン」ボタンをクリックします。](/help/analyze/report-builder/assets/rb_login.png)

1. Adobe Experience ID アカウント情報を入力します。アカウント情報は、Adobe Analyticsの資格情報と一致する必要があります。

   ![&#x200B; ログインアイコンと組織。](/help/analyze/report-builder/assets/image4.png)

ログインすると、パネルの上部にログインアイコンと組織が表示されます

## 組織の切り替え

最初のログインでは、プロファイルに割り当てられたデフォルトの組織にログインすることになります。

1. ログイン時に表示された組織の名前をクリックします。

1. 使用可能な組織のリストから組織を選択します。自身がアクセス権を持っている組織のみが表示されます。

   ![&#x200B; アクセスできる組織のリスト &#x200B;](/help/analyze/report-builder/assets/image5.png)

## ログアウト

ユーザープロファイルで Report Builder からログアウトできます。

1. 開いているワークブックに加えた変更を保存します。

1. アバターアイコンをクリックして、ユーザープロファイルを表示します。

   ![&#x200B; ユーザープロファイルのアバターと「ログアウト」ボタン &#x200B;](/help/analyze/report-builder/assets/image6.png)

1. 「**ログアウト**」をクリックします。
