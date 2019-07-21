---
description: Adobe Analytics 導入のための Dynamic Tag Management の「一般」設定のフィールド説明です。
keywords: Analyticsの導入;導入方法、Dynamic Tag Management;dtm;一般設定;euコンプライアンス;文字セット;currency code;トラッキングサーバー;sslトラッキングサーバー
seo-description: Adobe Analytics 導入のための Dynamic Tag Management の「一般」設定のフィールド説明です。
seo-title: 全般
solution: Analytics
title: 全般
topic: 開発者と導入
uuid: 93008719-6fb6-4e39-9a75- c937fe3247b9
translation-type: tm+mt
source-git-commit: 49c81e50ff10060ef7a3debe82132d1099e25118

---


# 全般

Adobe AnalyticsをデプロイするためのDTMの一般設定のフィールドの説明です。

**[!UICONTROL &lt;プロパティ&gt;]** / ![](assets/settings_gear.png)**[!UICONTROL ツール]** を編集/ **[!UICONTROL 一般]**

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
     <li id="li_227CB14326344AA3980F20C7EACF2AD2"> <p> Cookie が存在しない場合または Cookie が存在していても<span class="term"> true </span>の場合、この設定を有効にするとツールの読み込みはスキップされます。つまり、ツールを使用するルールのどの部分も適用されません。 </p> <p>ルールで Analytics の EU コンプライアンスがオンになっていて、ルールにサードパーティコードが含まれ、その Cookie が <span class="term"> false </span>の場合、サードパーティコードは実行されます。ただし、Analytics 変数は設定されません。 </p> </li> 
     <li id="li_1E74E02D7E4646ACA86D862A1D3C6679"> Cookie が存在し、<span class="term"> true </span>の場合、ツールは通常どおり読み込まれます。 </li> 
    </ul> <p>You are responsible for setting the <span class="filepath"> sat_track </span> (or custom named) cookie to <span class="term"> false </span> if a visitor opts out. 次のカスタムコードを実行することでこれを達成できます： </p> <p> 
     <code>_ satellite. setCookie（"sat_ track"，&amp; amp;nbsp;"false"）; </code>
  </p> <p> You must also have a mechanism to set that cookie to <span class="term"> true </span> if you want a visitor to be able to opt in later: </p> <p> 
     <code>_ satellite. setCookie（"sat_ track"，&amp; amp;nbsp;"true"）; </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文字セット </p> </td> 
   <td colname="col2"> <p>利用できる文字エンコーディングセットを表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>通貨コード </p> </td> 
   <td colname="col2"> <p>サポートされている通貨コードを選択のために表示します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>トラッキングサーバー </p> </td> 
   <td colname="col2"> <p>イメージリクエストおよび Cookie が記述されたドメイン。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SSL トラッキングサーバー </p> </td> 
   <td colname="col2"> <p>イメージリクエストおよび Cookie が記述されたドメイン。セキュリティ保護されているページで使用されます。If定義されていない場合、SSL データは  <span class="term"> trackingServer </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>データセンター </p> </td> 
   <td colname="col2"> <p>データ収集に使用される Adobe データセンター。 </p> </td> 
  </tr> 
 </tbody> 
</table>

