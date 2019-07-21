---
description: すべての製品が特定の期間に発生させた収益の量を測定します。
seo-description: すべての製品が特定の期間に発生させた収益の量を測定します。
seo-title: 売上高
solution: Analytics
title: 売上高
topic: レポート
uuid: e5b72798- f5c7-440d- a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 売上高 

すべての製品が特定の期間に発生させた収益の量を測定します。

売上高を使用して、サイトの一般的な成功とトレンドを表示できます。また、このレポートを使用してサイトが特に成功していた期間を特定し、そのソースを見つけて将来のキャンペーンに使用することもできます。

## レポートの一般的なプロパティ {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* このレポートが正しくデータを収集するために満たす必要のある要件があります。同じイメージリクエスト内で以下のことが起きる必要があります。

   * [!UICONTROL 購入]イベントが       `s.events` 変数に設定されている値と同じ。

   * `products` 変数が価格フィールドで値と共に定義されている必要があります。
   * この例では $35.99 が売上高レポートに渡されます。

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* [!UICONTROL s.products] 変数内に複数の製品がある場合、すべてが売上高レポートに含められます。For example, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] would pass $9 in revenue to reporting.

   >[!NOTE]
   >
   >単一製品で数量が増加すると、売上高は乗算されません。For example, [!DNL s.products="Womens;Socks;5;4.50"] does not pass $22.50 into reporting, it passes $4.50. Make sure your implementation passes the total revenue for the quantity listed ( [!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL 売上高]では、ある期間での合計金額が最も近い通貨値に丸められます。それぞれの個別製品やヒットが丸められることはありません。
* Analytics では、それぞれの日が最も近い整数の通貨に丸められるので、それぞれの日の合計を月別合計と比較すると、非常に小さい金額のずれがあります。これは、月別合計が丸められたそれぞれの日の合計ではなく、合計を最も近い整数の通貨に丸めた値であるためです。
* 売上高が最も近い通貨に丸められないレポートを作成するには、      [計算指標](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/)を使用します。
* `purchaseID` 変数を使用しない限り、ユーザーがページを更新すると、このデータがアドビに複数回送信されるので、売上高が水増しされる場合があります。
* 時間別の分類はレポートスイートのタイムゾーンに基づいています。
* このレポートには行項目は含まれていません。トレンドフォーマットでのみ表示できます。
* 時間、日、週、月、四半期、および年の精度を適用できます。これらの精度はレポートの日付範囲に応じて使用できます。
* このレポートは、以下のレポートによって分類できます（組織とレポートスイートの設定によって異なります）。

   * [!UICONTROL 訪問別滞在時間レポート.]
   * [!UICONTROL ページとサイトセクション]レポート。
   * [!UICONTROL ビデオ]レポート。
   * [!UICONTROL ページの深さと入口ページ]レポート。
   * ほとんどの[!UICONTROL トラフィックソース]レポート（[!UICONTROL 検索キーワード]、[!UICONTROL 検索エンジン]、および[!UICONTROL 参照ドメイン]レポートを含む）。

   * [!UICONTROL トラッキングコード]レポートと、関連付けられたすべての分類レポート。
   * [!UICONTROL トラッキングコード]レポートと、関連付けられたすべての分類レポート。[!UICONTROL カテゴリ]レポート。

   * ほとんどすべての[!UICONTROL 訪問者プロファイル]レポート（[!UICONTROL 地理特性]レポートを除く）。

   * 基本的な下位関係を持つすべての[!UICONTROL カスタムコンバージョン]変数レポート。

* 時間別の分類は使用できません。

## 製品固有のプロパティ {#section_ED87FFD020634453AABE86B0248BE69B}

* This report can be accessed by going to **[!UICONTROL Conversion]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* [!UICONTROL トラフィックソース]分類は、[!UICONTROL 検索方法]の下にあります。

* This report can be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* 上記のすべての分類に加え、[!UICONTROL ファーストタッチおよびラストタッチマーケティングチャネル]分類を使用できます。

* This report can also be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* 前述の分類に加え、[!UICONTROL リスト]変数と現在の[!UICONTROL ビデオ]変数を使用できます。

* このレポートではセグメントを利用できます。

* 他のすべてのレポートと変数によってこのレポート内の各項目を分類し、任意の精度で分類を表示できます。
* すべての[!UICONTROL コンバージョン]および[!UICONTROL トラフィック]指標を[!UICONTROL 売上高]と共に使用できます。すべての[!UICONTROL コンバージョン]指標について様々な配分を使用できます。

* このレポートでは複数の高度なアドバンスセグメントを使用できます。

このレポートが必要な場所で使用できない場合は、管理者にお問い合わせください。組織独自のニーズに合わせてデフォルト名やメニュー構造が変更されている場合があります。
