---
description: リテラル用のData Connectors統合では、Analytics変数を使用して、様々なリテラル指標を追跡します。
seo-description: リテラル用のData Connectors統合では、Analytics変数を使用して、様々なリテラル指標を追跡します。
seo-title: Analytics 変数
title: Analytics 変数
uuid: 4d5e087c- f495-4aab-9ad1-9b901d34a254
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics 変数{#analytics-variables}

リテラル用のData Connectors統合では、Analytics変数を使用して、様々なリテラル指標を追跡します。

After identifying the Event and eVars to use with the emarsys integration, enable them in the [Admin Console](https://microsite.omniture.com/t2/help/en_US/reference/index.html?f=conversion_var_admin).

**必須の変数**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数の種類 </th> 
   <th colname="col2" class="entry"> 名前 </th> 
   <th colname="col3" class="entry"> セット方法 </th> 
   <th colname="col4" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> 合計バウンス </td> 
   <td colname="col3"> <p>marsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>合計バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> クリック済み </td> 
   <td colname="col3"> <p>marsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>クリックイベントにより、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> 開封済み </td> 
   <td colname="col3"> <p>marsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>開封イベントでは、電子メールメッセージを開いた訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> 送信済み </td> 
   <td colname="col3"> <p>marsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>Sendイベントを使用すると、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> 登録解除 </td> 
   <td colname="col3"> <p>marsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>登録解除イベントを使用すると、電子メールを開いた訪問者の数を確認して、組織からの将来の電子メールメッセージをオプトアウトするための登録解除リンクをクリックできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>自動収集方法またはJavaScriptプラグインを介して電子メールリンクのクエリパラメーターから収集されます。 </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVarまたはs. campaign </td> 
   <td colname="col2"> メッセージID </td> 
   <td colname="col3"> <p>自動収集方法またはJavaScriptプラグインを介して電子メールリンクのクエリパラメーターから収集されます。 </p> </td> 
   <td colname="col4"> この値はしばしばキャンペーン変数に格納されます。 </td> 
  </tr> 
 </tbody> 
</table>

