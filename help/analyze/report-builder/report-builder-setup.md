---
title: Report Builderの設定
description: Adobe Analytics Report Builder for Excelのインストールと設定に関する完全なガイドを学習します。 シームレスな統合のためのステップバイステップのセットアップ手順。
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
TQID: https://experienceleague.adobe.com/a7cYk3fdAL90KUUllMaAmlhqrNPSboBmOoQ9gaPbDWg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 564
ht-degree: 40%

---

# Report Builderの設定

この記事では、[!DNL Microsoft] [!DNL Excel]でAdobe AnalyticsにReport Builderを使用するための要件について説明します。 アドインのインストール方法や設定方法を説明します。

## 要件

Report Builder Adobe Analytics版は、次のオペレーティングシステムおよびweb ブラウザーでサポートされています。

### macOS

- macOS バージョン 10.x 以降
- すべての[!DNL Microsoft] [!DNL Excel] バージョン

### Windows

- Windows 10、バージョン 1904 以降
- [!DNL Excel] バージョン 2106以降

  すべてのWindows デスクトップ [!DNL Excel] ユーザーは、アドインを使用するためにMicrosoft Edge Webview2をインストールする必要があります。 コントローラーをインストールするには：

   1. <https://aka.ms/webview2installer> にアクセスします。
   1. Evergreen スタンドアロンインストーラーを選択してダウンロードします。
   1. インストールプロンプトに従います。

### Web Office

- すべてのブラウザーとバージョンをサポート


## Report Builder Excel アドイン

Adobe Analyticsで[!DNL Report Builder]を使用するには、Report Builder [!DNL Excel] アドインをインストールする必要があります。 Report Builder [!DNL Excel] アドインをインストールすると、開いている[!DNL Excel] ブック内からReport Builderにアクセスできます。

### Report Builder アドインのダウンロードとインストール

Report Builder アドインをダウンロードしてインストールするには

1. [!DNL Excel]を起動し、新しいワークブックを開きます。

1. **[!UICONTROL 挿入]**/**[!UICONTROL アドインを取得]**&#x200B;を選択します。

1. Office アドインダイアログで、「ストア」タブを選択します。

1. 「Report Builder」を検索し、**[!UICONTROL 追加]**&#x200B;をクリックします。

1. ライセンス条件とプライバシーポリシーのダイアログボックスで、**[!UICONTROL 続行]**&#x200B;をクリックします。

**「ストア」タブが表示されない場合**

1. [!DNL Excel]で、ファイル/アカウント/設定を管理を選択します。

1. 「オプションの接続されたエクスペリエンスを有効にする」の横のボックスをオンにします。

1. [!DNL Excel]を再起動します。

**組織が Microsoft ストアへのアクセスをブロックしている場合**

- IT またはセキュリティチームに連絡して、Report Builder アドインの承認をリクエストします。 承認が付与されたら、Office アドインダイアログで「**[!UICONTROL 管理者管理]**」タブを選択します。

  ![Office アドインダイアログの「管理者管理」タブ。](./assets/image1.png)

- または、[&#x200B; マニフェストファイル &#x200B;](https://reportbuilder.an.adobe.com/manifest.xml)を手動で取得し、独自のIT インフラストラクチャ上でファイルをホストすることもできます。 <br/>Microsoft ストアから提供されていないExcel マニフェスト ファイルをインストールする方法については、Microsoft Office [&#x200B; オンライン ドキュメント &#x200B;](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish)に従ってください。

Report Builder アドインをインストールすると、「ホーム」タブの下の[!DNL Excel] リボンにReport Builder アイコンが表示されます。

![ExcelのReport Builder アイコン &#x200B;](/help/analyze/report-builder/assets/rb_app_icon.png)

## Report Builder へのログイン

オペレーティングシステムまたはブラウザーにReport Builder for Excel アドインをインストールしたら、次の手順に従ってReport Builderにログインします。

1. Excel ワークブックを開きます。

1. Report Builder アイコンをクリックして、Report Builder を起動します。

1. Adobe Report Builder ツールバーで、「**[!UICONTROL ログイン]**」をクリックします。

   ![Report Builder ログインボタンをクリックします。](/help/analyze/report-builder/assets/rb_login.png)

1. Adobe Experience ID アカウント情報を入力します。 アカウント情報は、Adobe Analyticsの資格情報と一致している必要があります。

   ![&#x200B; ログインアイコンと組織。](/help/analyze/report-builder/assets/image4.png)

ログインすると、ログインアイコンと組織がパネルの上部に表示されます

## 組織の切り替え

最初のログインでは、プロファイルに割り当てられたデフォルトの組織にログインすることになります。

1. ログイン時に表示された組織の名前をクリックします。

1. 使用可能な組織のリストから組織を選択します。 自身がアクセス権を持っている組織のみが表示されます。

   ![&#x200B; アクセスできる組織のリスト。](/help/analyze/report-builder/assets/image5.png)

## ログアウト

ユーザープロファイルで Report Builder からログアウトできます。

1. 開いているワークブックに加えた変更を保存します。

1. アバターアイコンをクリックして、ユーザープロファイルを表示します。

   ![&#x200B; ユーザープロファイルのアバターとログアウトボタン。](/help/analyze/report-builder/assets/image6.png)

1. 「**ログアウト**」をクリックします。
