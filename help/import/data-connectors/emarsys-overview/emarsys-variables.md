---
description: emarsys 用 Data Connectors 統合は、Analytics 変数を使用してさまざまな emarsys 指標を追跡します。
title: Analytics 変数
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 100%

---


# Analytics 変数 {#analytics-variables}

emarsys 用 Data Connectors 統合は、Analytics 変数を使用してさまざまな emarsys 指標を追跡します。

emarsys 統合で使用するイベントと eVar を特定したら、[Admin Console](https://docs.adobe.com/content/help/ja-JP/analytics/admin/admin-tools/c-admin-tools.html) でそれらを有効にします。

**必須変数**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 変数の種類 </th> 
   <th colname="col2" class="entry"> 名前 </th> 
   <th colname="col3" class="entry"> 母集団メソッド </th> 
   <th colname="col4" class="entry"> 説明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> イベント（数値） </td> 
   <td colname="col2"> バウンス数合計 </td> 
   <td colname="col3"> <p>emarsys から自動的に読み込み </p> </td> 
   <td colname="col4"> <p>バウンス数合計イベントを使用すると、配信の問題が原因で受信者に配信されなかった電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント（数値） </td> 
   <td colname="col2"> クリック済み </td> 
   <td colname="col3"> <p>emarsys から自動的に読み込み </p> </td> 
   <td colname="col4"> <p>クリックイベントを使用すると、電子メールメッセージをクリックした訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント（数値） </td> 
   <td colname="col2"> 開封済み </td> 
   <td colname="col3"> <p>emarsys から自動的に読み込み </p> </td> 
   <td colname="col4"> <p>開封済みイベントを使用すると、電子メールメッセージを開封した訪問者の数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント（数値） </td> 
   <td colname="col2"> 送信済み </td> 
   <td colname="col3"> <p>emarsys から自動的に読み込み </p> </td> 
   <td colname="col4"> <p>送信数イベントを使用すると、送信された電子メールメッセージの数を確認できます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> イベント（数値） </td> 
   <td colname="col2"> 登録解除 </td> 
   <td colname="col3"> <p>emarsys から自動的に読み込み </p> </td> 
   <td colname="col4"> <p>登録解除イベントを使用すると、電子メールメッセージを開いた訪問者の数を確認できます。組織からの今後の電子メールメッセージをオプトアウトするには、登録解除リンクをクリックします。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 受信者 ID </td> 
   <td colname="col3"> <p>自動収集方法または JavaScript プラグインを使用して、電子メールリンクのクエリパラメーターから収集されます。 </p> </td> 
   <td colname="col4"> 受信者 ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar または s.campaign </td> 
   <td colname="col2"> メッセージ ID </td> 
   <td colname="col3"> <p>自動収集方法または JavaScript プラグインを使用して、電子メールリンクのクエリパラメーターから収集されます。 </p> </td> 
   <td colname="col4"> この値は、多くの場合、キャンペーン変数に保存されます。 </td> 
  </tr> 
 </tbody> 
</table>

