---
description: すべての製品が特定の期間に発生させた収益の量を測定します。
title: 売上高
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 売上高

すべての製品が特定の期間に発生させた収益の量を測定します。

売上高を使用して、サイトの一般的な成功とトレンドを表示できます。また、このレポートを使用してサイトが特に成功していた期間を特定し、そのソースを見つけて将来のキャンペーンに使用することもできます。

## レポートの一般的なプロパティ {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* このレポートが正しくデータを収集するために満たす必要のある要件があります。同じイメージリクエスト内で以下のことが起きる必要があります。

   * 変数内 [!UICONTROL purchase] でイベントを起動する必要があ `s.events` ります。

   * `products` 変数が価格フィールドで値と共に定義されている必要があります。
   * この例では $35.99 が売上高レポートに渡されます。

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* [!UICONTROL s.products] 変数内に複数の製品がある場合、すべてが売上高レポートに含められます。例えば、[!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] では $9 が収益としてレポートに渡されます。

   >[!NOTE]
   >
   >単一の製品で量が増加した場合、売上高は乗算されません。例えば、[!DNL s.products="Womens;Socks;5;4.50"] では $22.50 ではなく、$4.50 がレポートに渡されます。実装において、リストされている量に対する合計売上高を渡すようにしてください（[!DNL s.products="Womens;Socks;5;22.50"]）に対する合計売上高を渡すようにしてください。

* [!UICONTROL Revenue] 期間の合計金額を最も近い通貨値に丸めます。 それぞれの個別製品やヒットが丸められることはありません。
* Analytics では、それぞれの日が最も近い整数の通貨に丸められるので、それぞれの日の合計を月別合計と比較すると、非常に小さい金額のずれがあります。これは、月別合計が丸められたそれぞれの日の合計ではなく、合計を最も近い整数の通貨に丸めた値であるためです。
* 売上高が最も近い通貨に丸められないレポートを作成するには、          [計算指標](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/cm-overview.html)を使用します。
* `purchaseID` 変数を使用しない限り、ユーザーがページを更新すると、このデータがアドビに複数回送信されるので、売上高が水増しされる場合があります。
* 時間別の分類はレポートスイートのタイムゾーンに基づいています。
* このレポートには行項目は含まれていません。トレンドフォーマットでのみ表示できます。
* 時間、日、週、月、四半期、および年の精度を適用できます。これらの精度はレポートの日付範囲に応じて使用できます。
* このレポートは、以下のレポートによって分類できます（組織とレポートスイートの設定によって異なります）。

   * [!UICONTROL Time Spent per Visit] レポート.
   * [!UICONTROL Pages and Site Sections] レポート.
   * [!UICONTROL Videos] レポート.
   * [!UICONTROL Page Depth and Entry Pages] レポート.
   * レポー [!UICONTROL Traffic Sources]ト、レポー [!UICONTROL Search Keywords]トを含む [!UICONTROL Search Engines]ほとんどのレ [!UICONTROL Referring Domains] ポート。

   * [!UICONTROL Tracking Code] レポートおよびすべての関連する分類レポート。
   * [!UICONTROL Products variable] レポートおよびすべての関連する分類レポート。 また、レポ [!UICONTROL Categories] ートです。

   * レポートを除く、ほ [!UICONTROL Visitor Profile] とんどすべてのレポ [!UICONTROL GeoSegmentation] ート。

   * すべての変 [!UICONTROL Custom Conversion] 数は、基本的な下位関係を持つレポートです。

* 時間別の分類は使用できません。

## 製品固有のプロパティ {#section_ED87FFD020634453AABE86B0248BE69B}

* This report can be accessed by going to **[!UICONTROL Conversion]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] 内訳は、を参照してくださ [!UICONTROL Finding Methods]い。

* This report can be accessed by going to **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* 前述のすべての分類に加えて、分類も使 [!UICONTROL First and Last Touch Marketing Channel] 用できます。

* This report can also be accessed by going to **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* In addition to the previously mentioned breakdowns, [!UICONTROL List]variables and the current [!UICONTROL Video] variables can be used.

* このレポートではセグメントを利用できます。

* 他のすべてのレポートと変数によってこのレポート内の各項目を分類し、任意の精度で分類を表示できます。
* すべての指標と指標を同時 [!UICONTROL conversion] に使用 [!UICONTROL traffic] できま [!UICONTROL Revenue]す。 You can use different allocation for all [!UICONTROL conversion] metrics.

* このレポートでは複数の高度なアドバンスセグメントを使用できます。

このレポートが必要な場所で使用できない場合は、管理者にお問い合わせください。組織独自のニーズに合わせてデフォルト名やメニュー構造が変更されている場合があります。
