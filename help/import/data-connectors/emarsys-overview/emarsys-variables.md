---
description: emarsys用のData Connectors統合では、Analytics変数を使用して様々なemarsys指標を追跡します。
seo-description: emarsys用のData Connectors統合では、Analytics変数を使用して様々なemarsys指標を追跡します。
seo-title: Analytics 変数
title: Analytics 変数
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analytics 変数{#analytics-variables}

emarsys用のData Connectors統合では、Analytics変数を使用して様々なemarsys指標を追跡します。

emarsys統合で使用するイベントとeVarを特定したら、管理コンソールでそれらを有 [効にします](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/c-admin-tools.html)。

**必須変数**

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
   <td colname="col2"> 合計バウンス数 </td> 
   <td colname="col3"> <p>emarsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>合計バウンスイベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> クリック済み </td> 
   <td colname="col3"> <p>emarsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>クリック済みイベントを使用すると、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> 開封済み </td> 
   <td colname="col3"> <p>emarsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>Openedイベントを使用すると、電子メールメッセージを開いた訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> 送信済み </td> 
   <td colname="col3"> <p>emarsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>Sendsイベントを使用すると、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event（数値） </td> 
   <td colname="col2"> 登録解除 </td> 
   <td colname="col3"> <p>emarsysから自動的にインポート </p> </td> 
   <td colname="col4"> <p>「購読解除」イベントを使用すると、電子メールを開いた訪問者の数を確認し、「購読解除」リンクをクリックして、組織からの今後の電子メールメッセージをオプトアウトできます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>自動収集方法またはJavaScriptプラグインを使用して、電子メールリンクのクエリパラメーターから収集されます。 </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar またはs.campaign </td> 
   <td colname="col2"> メッセージID </td> 
   <td colname="col3"> <p>自動収集方法またはJavaScriptプラグインを使用して、電子メールリンクのクエリパラメーターから収集されます。 </p> </td> 
   <td colname="col4"> この値は、多くの場合、campaign変数に格納されます。 </td> 
  </tr> 
 </tbody> 
</table>

