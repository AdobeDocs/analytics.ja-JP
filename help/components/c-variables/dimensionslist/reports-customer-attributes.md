---
description: 顧客属性に関する Analytics の FAQ と顧客属性レポートの実行方法です。
seo-description: 顧客属性に関する Analytics の FAQ と顧客属性レポートの実行方法です。
seo-title: 顧客属性
solution: Experience Cloud,Analytics
title: 顧客属性
uuid: 94721265-ba23-45d5-8807-76f81b0b8a30
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 顧客属性

顧客属性に関する Analytics の FAQ と顧客属性レポートの実行方法です。

**[!UICONTROL レポート]** /訪問者プロファイル **[!UICONTROL /顧]****[!UICONTROL 客属性]**

エンタープライズ顧客データを顧客関係管理（CRM）データベースに取り込んでいる場合は、そのデータを Experience Cloud の顧客属性データソースにアップロードできます。データがアップロードされると、Reports &amp; Analytics の顧客属性レポートを実行できます。

* [Analytics の顧客属性とレポート指標](../../../components/c-variables/dimensionslist/reports-customer-attributes.md#section_EF343662146B460A882D3DF772ADD86D)
* [FAQ - Analytics の顧客属性](../../../components/c-variables/dimensionslist/reports-customer-attributes.md#section_E29641D1F3D649C1AC9EA5231921F038)

顧客属性データのアップロードについて詳しくは、Experience Cloud ヘルプの[顧客属性](https://marketing.adobe.com/resources/help/en_US/mcloud/index.html?f=attributes)を参照してください。

## Analytics の顧客属性とレポート指標 {#section_EF343662146B460A882D3DF772ADD86D}

顧客属性をアップロードし、（Experience cloudで）スキーマを検証した後、属性文字列と整数にマップしたわかりやすい名前( *`age`* またはな *`gender`*&#x200B;ど)に基づいて指標が作成されます。 These metrics appear in **[!UICONTROL Visitor Profile]** &gt; **[!UICONTROL Customer Attributes]** reports.

次に例を示します。

**[!UICONTROL 訪問者プロファイル]** / **[!UICONTROL 顧客属性]** /年 **[!UICONTROL 齢]**

![](assets/report_age.png)

**例 - 年齢指標**

文字列を *`age`*, the system creates the following metrics and dimensions:

* 年齢ディメンション：年齢属性に基づいてレポートを実行できます。
* 年齢指標：個別訪問者数レポートなどのレポートに追加できる指標です。
* 年齢の数指標：例えば、訪問者がフォームで&#x200B;*`age`*&#x200B;の値を指定しているかどうかを把握できます。

指標は、レポート表の概要なので、平均年齢を示す      [計算指標を作成する](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/)必要があります。The formula for this metric is `Age / Count of Age`.

## FAQ - Analytics の顧客属性 {#section_E29641D1F3D649C1AC9EA5231921F038}

<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 質問 </th> 
   <th colname="col2" class="entry"> 回答 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>propまたはeVarに顧客IDを入力する代わりに、IDサービスを使用して顧客IDを設定する方がよいのはなぜですか。 </p> </td> 
   <td colname="col2"> <p>IDサービスを使用すると、次のような多くの利点があります。 </p> 
    <ul id="ul_5D3659604D43419F9CA5920B4F93728E"> 
     <li id="li_BA2EF0715C5A47EFAFA7191CFAD088A4">Customer IDをIDサービスと共に設定しない場合、顧客レコードはAdobe Analyticsでのみ使用できます。 顧客レコードをリアルタイムターゲティングに使用する場合は、IDサービスを使用する必要があります。 </li> 
     <li id="li_228358684E474A298E39578D427BF932">IDサービスを使用して顧客IDを設定すると、IDをExperience cloudと同期するのにかかる時間が短縮されます。 顧客 ID を prop または eVar に入力すると、顧客 ID は、バッチで発生するバックエンドサーバー同期を通じて Experience Cloud に送信されます。IDサービスは、すぐに顧客IDをExperience cloudと同期します。 </li> 
     <li id="li_BCF28219E4014FCF9F747C3D8D270526"> propやeVarの代わりにIDサービスを使用すると、そのpropやeVarを解放して他の用途に使用できるようになります。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>既に顧客 ID を prop または eVar に保存している場合、prop や eVar を CRM 属性で分類する代わりに、この新しい機能を使用する理由は何ですか </p> </td> 
   <td colname="col2"> <p>prop および eVar は、「超過したユニーク数」の制限を受けます。この機能を使用することで、属性データを導入でき、顧客 ID に制限がなくなります。また、prop/eVar 方式の場合は、CRM 情報が利用できるのは Analytics のみに限られます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM 属性は Adobe Analytics ではどのように見えますか。 </p> </td> 
   <td colname="col2"> <p>CRM 属性は、Analysis Workspace、Reports &amp; Analytics、Ad Hoc Analysis、レポート API および Report Builder で利用可能です。テキスト属性がレポート／ディメンションとして表示されます。数値属性がディメンションおよび指標として表示されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM データは、Data Warehouse およびデータフィードで使用できるようになりますか。 </p> </td> 
   <td colname="col2"> <p>現在、CRM データは、Data Warehouse または Analytics データフィードで使用できません。 </p> </td> 
  </tr> 
 </tbody> 
</table>

