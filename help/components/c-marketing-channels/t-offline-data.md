---
description: オフラインデータをマーケティングチャネルレポートに追加します。
subtopic: Marketing channels
title: オフラインデータの追加
topic: Reports and analytics
uuid: bbf4661a-b6b1-4a89-a3cf-ae8dd785d37d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# オフラインデータの追加

オフラインデータをマーケティングチャネルレポートに追加します。

オンラインチャネルは、検索エンジン、インターネット広告、参照ドメイン、電子メールキャンペーンなどのリンク元からアクセスした訪問者のデータの分類に使用できます。オフラインチャネルは、テレビの CM、新聞、雑誌の広告などでサイトの情報を見つけて来訪した訪問者の分類に使います。

**マーケティングチャネルレポートへのデータソースの統合**

[データソースのデータ](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_faq.html)をマーケティングチャネルレポートに統合する場合は、次の事項に注意してください。

* 標準的なヒットが [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html) と共に Analytics レポートに渡されると、通常どおりマーケティングチャネルの処理ルールによって処理されます。
* `transactionID` のデータソースが Analytics に渡されると、標準的なヒットが処理されたマーケティングチャネルに自動的に関連付けられます。
* その他のデータソースのデータは、マーケティングチャネルの処理ルールによって処理されません。

データソースについて詳しくは、[データソース](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)ヘルプを参照してください。

オフラインチャネルのデータを分類するには、データソースでデータをアクティブにしてから、テンプレートをダウンロードして編集する必要があります。

[データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースの操作」を参照してください。

**オフラインデータの追加**

1. **[!UICONTROL 管理者]**／**[!UICONTROL データソース]**&#x200B;をクリックします。
1. データソースページで、「**[!UICONTROL 作成]**」をクリックします。
1. 「**[!UICONTROL 1. カテゴリの選択]**」で、「**[!UICONTROL オフラインチャネルデータ]**」を選択します。
1. 「**[!UICONTROL 2. タイプの選択]**」で、「**[!UICONTROL オフラインチャネルデータ]**」を選択します。
1. 「**[!UICONTROL アクティブ化]**」をクリックします。
1. データソース有効化ウィザードの指示に従って、オフライン指標をレポート指標にマッピングします。
1. テンプレートファイルをダウンロードし、Excel などのエディターソフトウェアで編集します。

   [データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースファイルの作成」を参照してください。

1. [データソースユーザーガイド](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html)の「データソースファイルのアップロード」で説明されているようにファイルをアップロードします。
