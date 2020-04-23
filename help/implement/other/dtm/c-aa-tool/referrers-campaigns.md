---
description: Adobe Analytics に Dynamic Tag Management をデプロイする際の、リファラーおよびキャンペーンオプション用の Dynamic Tag Management フィールドの説明です。
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: リファラーとキャンペーン
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# リファラーとキャンペーン

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL  *`Property`*]** /歯車 ![アイコン](assets/settings_gear.png)**[!UICONTROL Edit Tool]** > **[!UICONTROL Referrers & Campaigns]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 要素 </th>
   <th colname="col2" class="entry"> 説明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 転送者の上書き </td>
   <td colname="col2"> <p>s. <span class="varname"> 転送者変数に設定された値を上書きします</span> 。この値は、通常、ブラウザーに設定された転送者によって設定されます。 </p> <p>詳しくは、 <a href="../../../vars/page-vars/referrer.md">転送者</a>。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> キャンペーン </td>
   <td colname="col2"> <p>サイトに訪問者を導くために使用されるマーケティングキャンペーンを識別する変数。 通常、キャンペーンの値は、クエリー文字列パラメーターから取得します。 </p> <p>詳しくは、 <a href="../../../vars/page-vars/campaign.md">キャンペーン</a>。 </p> </td>
  </tr>
 </tbody>
</table>

DTM インターフェイスで、「クエリー文字列」と「値」（データ要素から取得できるもの）のどちらを使用するかを選択します。

![クエリーパラメーター](assets/dtm-queryparam.png)

インターフェイスにクエリー文字列を直接入力するか、キャンペーンをトラッキングする別の手段がある場合は別のデータ要素を参照することができます。
