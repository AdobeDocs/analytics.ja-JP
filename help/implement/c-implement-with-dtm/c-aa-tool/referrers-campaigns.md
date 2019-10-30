---
description: Adobe Analytics に Dynamic Tag Management をデプロイする際の、リファラーおよびキャンペーンオプション用の Dynamic Tag Management フィールドの説明です。
keywords: Dynamic Tag Management, リファラー, キャンペーン, リファラーの上書き, キャンペーン変数, クエリパラメーター
seo-description: Adobe Analytics に Dynamic Tag Management をデプロイする際の、リファラーおよびキャンペーンオプション用の Dynamic Tag Management フィールドの説明です。
seo-title: リファラーとキャンペーン
solution: Experience Cloud, Analytics, Dynamic Tag Management
title: リファラーとキャンペーン
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
   <td colname="col2"> <p>ブラウザーに設定されたリファラーではなく、<span class="varname"> s.referrer</span> 変数にセットされた値をリファラーとして使用します。 </p> <p>See <a href="/help/implement/js-implementation/c-variables/page-variables.md">Page Variables</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> キャンペーン </td> 
   <td colname="col2"> <p>訪問者をサイトに誘導するために使用されるマーケティングキャンペーンを識別する変数です。通常、キャンペーンの値は、クエリ文字列パラメーターから取得します。 </p> <p>See [<a href="/help/implement/js-implementation/c-variables/page-variables.md">Page Variables</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

DTM インターフェイスで、「クエリ文字列」と「値」（データ要素から所得できるもの）のどちらを使用するかを選択します。

![](assets/dtm-queryparam.png)

インターフェイスにクエリ文字列を直接入力するか、キャンペーンをトラッキングする別の手段がある場合は別のデータ要素を参照することができます。
