---
description: オフラインデータをマーケティングチャネルレポートに追加します。
seo-description: オフラインデータをマーケティングチャネルレポートに追加します。
seo-title: オフラインデータの追加
solution: Analytics
subtopic: マーケティングチャネル
title: オフラインデータの追加
topic: Reports and Analytics
uuid: bbf4661a- b6b1-4a89- a3cf- ae8dd785d37d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# オフラインデータの追加

オフラインデータをマーケティングチャネルレポートに追加します。

オンラインチャネルは、検索エンジン、インターネット広告、参照ドメイン、電子メールキャンペーンなどのリンク元からアクセスした訪問者のデータの分類に使用できます。オフラインチャネルは、テレビの CM、新聞、雑誌の広告などでサイトの情報を見つけて来訪した訪問者の分類に使います。

**マーケティングチャネルレポートへのデータソースの統合**

[データソースのデータ](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_faq)をマーケティングチャネルレポートに統合する場合は、次の事項に注意してください。

* 標準的なヒットが [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID) と共に Analytics レポートに渡されると、通常どおりマーケティングチャネルの処理ルールによって処理されます。
* `transactionID` のデータソースが Analytics に渡されると、標準的なヒットが処理されたマーケティングチャネルに自動的に関連付けられます。
* その他のデータソースのデータは、マーケティングチャネルの処理ルールによって処理されません。

データソースについて詳しくは、[データソース](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)ヘルプを参照してください。

オフラインチャネルのデータを分類するには、データソースでデータをアクティブにしてから、テンプレートをダウンロードして編集する必要があります。

[データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースの操作」を参照してください。

**オフラインデータの追加**

1. **[!UICONTROL 管理者]** / **[!UICONTROL データソース]**&#x200B;の順にクリックします。
1. データソースページで、「**[!UICONTROL 作成]」をクリックします。**
1. Under **[!UICONTROL 1. Select Category]**, select **[!UICONTROL Offline Channel Data]**.
1. Under **[!UICONTROL 2. Select Type]**, select **[!UICONTROL Offline Channel Data]**.
1. Click **[!UICONTROL Activate.]**
1. データソース有効化ウィザードの指示に従って、オフライン指標をレポート指標にマッピングします。
1. テンプレートファイルをダウンロードし、Excel などのエディターソフトウェアで編集します。

   [データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースファイルの作成」を参照してください。

1. [データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースファイルのアップロード」で説明されているようにファイルをアップロードします。
