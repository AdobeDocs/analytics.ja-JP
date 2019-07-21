---
description: 購入イベントでは、Analytics 変数を使用して特定の購入情報を取り込みます。s.purchaseID 変数を使用して、イベントをシリアル化（重複排除）します。
keywords: Analytics の導入
seo-description: 購入イベントでは、Analytics 変数を使用して特定の購入情報を取り込みます。s.purchaseID 変数を使用して、イベントをシリアル化（重複排除）します。
seo-title: 購入イベント
solution: Analytics
title: 購入イベント
topic: 開発者と導入
uuid: d90cec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 購入イベント

購入イベントでは、Analytics 変数を使用して特定の購入情報を取り込みます。s.purchaseID 変数を使用して、イベントをシリアル化（重複排除）します。

The *`purchaseID`* is limited to 20 characters. *`purchaseID`* 変数は、[!UICONTROL s.events] 変数に渡されたすべてのイベントをシリアル化して、イベントのシリアル化値を上書きします。If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

*`purchaseID`* なしで購入イベントが呼び出された場合、*`s.products`* 変数と *`s.events`変数に基づいて、固有の purchaseID が自動的に生成されます。*&#x200B;このように自動生成された *`purchaseID`は、訪問者のブラウザーにローカルの cookie 値として保存され、レポートスイートテーブルに送られることはありません。* Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

訪問者が購入をおこなう際には、次のチェックが実施されます。

* この変数は、*`purchaseID`* が 5 個の cookie 値のいずれかと一致しているかどうか。一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
* If *`purchaseID`* is defined, does it match any value in the report suite's back-end table? 一致している場合、そのイメージリクエストは重複した購入であると見なされます。購入イベントを含むコンバージョン変数はすべて、レポートに表示されません。
* *`purchaseID`* が、cookie に保存された直近の 5 個の値に一致せず、レポートスイートの *`purchaseID`テーブルにも含まれていない場合、そのイメージリクエストは一意であり、レポートに含まれます。*&#x200B;例えば、ローカル cookie に既に 5 回の購入が記録されている場合、最も古い購入が上書きされます。

サーバーサイドの特定のコードを使用して、HTML ソースに埋め込む一意の番号（英数字の値）を生成できます。通常は、注文 ID またはこれに類似した英数字の値が使用されます。ユーザーがページを更新する場合、この値を変更しないでください。簡単な例を次に示します（*`purchaseID`* のコードはボールドで示しています）。

## 構文{#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 
```

## 例 {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## 追加情報 {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* イベント用の一意の識別子を生成する場合は、必ずサーバーサイドのコードを使用してください。JavaScript のランダム化関数を使用して番号を生成しないでください。この関数を使用すると、ページが読み込まれるたびに（[!UICONTROL インスタンス]／[!UICONTROL ページビュー]のカウントごとに）一意の番号が生成されます。

* 一意の識別子はすべてのセッションのすべてのユーザーに適用できます。したがって、ユーザーおよびセッション間で一意の識別子が生成されることを確認してください。例えば、ある注文 ID が 30 日後に再び使用される場合は、注文日を追加して[!UICONTROL 注文 ID] を一意なものにします。
* シリアル化値には、最長 20 文字の英数字の値を使用できます。これは、[!UICONTROL s.purchaseID]（G コードの場合は「s.」を「s_」に置き換えます）の制限と同じです。
* [!UICONTROL s.purchaseID] 変数は、[!UICONTROL s.events] 変数に渡されたすべてのイベントをシリアル化して、イベントのシリアル化値を上書きします。現在のページに対して [!UICONTROL s.purchaseID] 変数（G コードの場合は「s.」を「s_」に置き換えます）が使用される場合は、[!UICONTROL イベントのシリアル化]を使用しないでください。

