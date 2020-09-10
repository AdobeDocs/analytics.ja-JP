---
description: Adobe Analytics 導入のための Dynamic Tag Management の「一般」設定のフィールド説明です。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;general settings;eu compliance;character set;currency code;tracking server;ssl tracking server
title: 一般
topic: Developer and implementation
uuid: 93008719-6fb6-4e39-9a75-c937fe3247b9
translation-type: tm+mt
source-git-commit: 0d699a50a764d9ea76771118c7cc083fb46cefe9
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 100%

---


# 一般

Adobe Analytics の実装のための DTM の「一般」設定のフィールド説明です。

**[!UICONTROL *`Property`*]**／![](assets/settings_gear.png)**[!UICONTROL ツールを編集]**／**[!UICONTROL 一般]**

<table id="table_DD8DA303698041D296DD5DB080AF7971"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="keyword">Adobe Analytics</span> の EU コンプライアンスを有効にする  </p> </td> 
   <td colname="col2"> <p> EU プライバシー Cookie に基づいたトラッキングを有効または無効にします。 </p> <p>ページが読み込まれる際に、システムは、<span class="filepath">sat_track</span> という名前（または<span class="wintitle">プロパティ編集</span>ページで変更したカスタム名）の Cookie が設定されているかどうかを確認します。次の情報を考慮してください。 </p> 
    <ul id="ul_42A6D728F0BC4FBABB0069EFB66DCB01"> 
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Cookie が存在しない場合または Cookie が存在していても<span class="term"> true </span> 以外に設定されている場合、この設定を有効にするとツールの読み込みはスキップされます。つまり、ツールを使用するルールのどの部分も適用されません。 </p> <p>ルールで Analytics の EU コンプライアンスがオンになっていて、ルールにサードパーティコードが含まれ、その Cookie が   <span class="term"> false </span> の場合、そのサードパーティコードは実行されます。ただし、Analytics 変数は設定されません。 </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Cookie が存在し、<span class="term"> true </span> に設定されている場合、ツールは通常どおり読み込まれます。 </li> 
    </ul> <p>訪問者がオプトアウトしている場合、<span class="filepath">sat_track</span>（またはカスタム名）cookie を <span class="term">false</span> に設定する必要があります。次のカスタムコードを実行することでこれを達成できます： </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"false"); 
     </code> </p> <p> また、訪問者が後でオプトインできるようにするには、次のように、cookie を <span class="term">true</span> に設定するメカニズムも必要です。 </p> <p> 
     <code>
       _satellite.setCookie("sat_track",&amp;nbsp;"true"); 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Character Set </p> </td> 
   <td colname="col2"> <p>利用できる文字エンコーディングセットを表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>通貨コード </p> </td> 
   <td colname="col2"> <p>サポートされている通貨コードを選択のために表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tracking Server </p> </td> 
   <td colname="col2"> <p>イメージリクエストおよび Cookie が記述されたドメイン。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL Tracking Server </p> </td> 
   <td colname="col2"> <p>イメージリクエストおよび Cookie が記述されたドメイン。セキュリティ保護されているページで使用されます。  定義されていない場合、SSL データは<span class="term"> trackingServer </span> に送られます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データセンター </p> </td> 
   <td colname="col2"> <p>データ収集に使用される Adobe データセンター。 </p> </td> 
  </tr> 
 </tbody> 
</table>

