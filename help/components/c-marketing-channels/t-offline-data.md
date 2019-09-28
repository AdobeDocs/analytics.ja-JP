---
description: オフラインデータをマーケティングチャネルレポートに追加します。
seo-description: オフラインデータをマーケティングチャネルレポートに追加します。
seo-title: オフラインデータの追加
solution: Analytics
subtopic: マーケティングチャネル
title: オフラインデータの追加
topic: Reports & Analytics
uuid: bbf4661a-b6b1-4a89-a3cf-ae8dd785d37d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# オフラインデータの追加

オフラインデータをマーケティングチャネルレポートに追加します。

オンラインチャネルは、検索エンジン、インターネット広告、参照ドメイン、電子メールキャンペーンなどのリンク元からアクセスした訪問者のデータの分類に使用できます。オフラインチャネルは、テレビの CM、新聞、雑誌の広告などでサイトの情報を見つけて来訪した訪問者の分類に使います。

**データソースのマーケティングチャネルレポートへの統合**

[データソースのデータ](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_faq.html)をマーケティングチャネルレポートに統合する場合は、次の事項に注意してください。

* 標準的なヒットが [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html) と共に Analytics レポートに渡されると、通常どおりマーケティングチャネルの処理ルールによって処理されます。
* `transactionID` のデータソースが Analytics に渡されると、標準的なヒットが処理されたマーケティングチャネルに自動的に関連付けられます。
* その他のデータソースのデータは、マーケティングチャネルの処理ルールによって処理されません。

データソースについて詳しくは、[データソース](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)ヘルプを参照してください。

オフラインチャネルのデータを分類するには、データソースでデータをアクティブにしてから、テンプレートをダウンロードして編集する必要があります。

[データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースの操作」を参照してください。

**オフラインデータの追加**

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. データソースページで、「**[!UICONTROL 作成]」をクリックします。**
1. **[!UICONTROL 1未満 Select Category]**, select **[!UICONTROL Offline Channel Data]**.
1. **[!UICONTROL 2. Select Type]**, select **[!UICONTROL Offline Channel Data]**.
1. Click **[!UICONTROL Activate.]**
1. データソース有効化ウィザードの指示に従って、オフライン指標をレポート指標にマッピングします。
1. テンプレートファイルをダウンロードし、Excel などのエディターソフトウェアで編集します。

   [データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースファイルの作成」を参照してください。

1. [データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースファイルのアップロード」で説明されているようにファイルをアップロードします。
