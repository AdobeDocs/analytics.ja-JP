---
title: clearVars
description: インスタンスオブジェクトから値をクリアします。
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 67%

---

# clearVars

シングルページアプリケーションなどの実装では、同じページの読み込み時に複数のヒットを送信する必要があります。`clearVars()` メソッドを使用して、後続のヒットに持続しないように変数値をクリアします。

このメソッドは引数を取らず、値を返しません。その唯一の目的は、インスタンスオブジェクトから変数の値をクリアすることです。このメソッドは、次の要素を `undefined` に設定します。

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Web SDK を使用した変数のクリア

Web SDK を使用してAdobeにデータを送信すると、すべての XDM データが自動的にクリアされます。

## Adobe Analytics拡張機能を使用した変数のクリア

ルールを設定する際に、「変数をクリア」アクションを設定します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で「+」アイコンをクリックします。
5. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」ドロップダウンリストをAdobe Analyticsに、「[!UICONTROL &#x200B; アクションタイプ &#x200B;]」を [!UICONTROL &#x200B; 変数をクリア &#x200B;] に設定します。

## AppMeasurementの s.clearVars （）と Analytics 拡張機能のカスタムコードエディター

Analytics オブジェクトインスタンスをインスタンス化した後、実装の任意の場所で `s.clearVars()` メソッドを呼び出すことができます。

```js
s.clearVars();
```
