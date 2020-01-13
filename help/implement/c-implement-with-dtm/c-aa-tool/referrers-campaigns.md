---
description: Adobe Analytics に Dynamic Tag Management をデプロイする際の、リファラーおよびキャンペーンオプション用の Dynamic Tag Management フィールドの説明です。
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: リファラーとキャンペーン
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: ht
source-git-commit: e9820869d16b8656ebebe11e397a3d7d8123fbcf

---


# リファラーとキャンペーン

Adobe [!DNL Analytics] に [!UICONTROL Dynamic Tag Management ]をデプロイする際の、リファラーおよびキャンペーンオプション用の [!UICONTROL Dynamic Tag Management] フィールドの説明です。

**[!UICONTROL *`Property`*]**／![](assets/settings_gear.png) **[!UICONTROL ツールの編集]**／**[!UICONTROL リファラーおよびキャンペーン]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> リファラーの上書き </td> 
   <td colname="col2"> <p>ブラウザーに設定されたリファラーではなく、<span class="varname"> s.referrer</span> 変数にセットされた値をリファラーとして使用します。 </p> <p><a href="/help/implement/js-implementation/page-variables/page-variables.md">ページ変数</a>を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> キャンペーン </td> 
   <td colname="col2"> <p>訪問者をサイトに誘導するために使用されるマーケティングキャンペーンを識別する変数です。通常、キャンペーンの値は、クエリー文字列パラメーターから取得します。 </p> <p><a href="/help/implement/js-implementation/page-variables/campaign.md">ページ変数</a>を参照してください。 </p> </td> 
  </tr> 
 </tbody> 
</table>

DTM インターフェイスで、「クエリー文字列」と「値」（データ要素から所得できるもの）のどちらを使用するかを選択します。

![](assets/dtm-queryparam.png)

インターフェイスにクエリー文字列を直接入力するか、キャンペーンをトラッキングする別の手段がある場合は別のデータ要素を参照することができます。
