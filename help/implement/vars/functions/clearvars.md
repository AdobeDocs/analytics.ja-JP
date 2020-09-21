---
title: clearVars
description: インスタンスオブジェクトの以下の値をクリアします。この関数は要素を削除します（要素を「undefined」に設定します）。
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '168'
ht-degree: 100%

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

## Adobe Experience Platform Launch の「変数をクリア」

ルールを設定する際に、「変数をクリア」アクションを設定します。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数をクリア]」に設定します。

## AppMeasurement および Launch カスタムコードエディターの s.clearVars()

Analytics オブジェクトインスタンスをインスタンス化した後、実装の任意の場所で `s.clearVars()` メソッドを呼び出すことができます。

```js
s.clearVars();
```
