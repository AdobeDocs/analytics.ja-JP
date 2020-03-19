---
title: clearVars
description: インスタンスオブジェクトの以下の値をクリアします。この関数は要素を削除します（要素を「undefined」に設定します）。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# clearVars

シングルページアプリケーションなどの実装では、同じページ読み込みで複数のヒットを送信する必要があります。 このメソッド `clearVars()` を使用して、後続のヒットに持続しないように変数値をクリアします。

このメソッドは引数を取らず、値を返しません。 その目的は、インスタンスオブジェクトから変数の値をクリアすることだけです。 このメソッドは、次の要素をに設定しま `undefined`す。

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

## Adobe Experience Platform Launchでの変数の消去

ルールを設定する際に、「変数をクリア」アクションを設定します。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Rules] 目的のルールをクリックします（またはルールを作成します）。
4. 下の「 [!UICONTROL Actions]+」アイコンをクリックします。
5. ドロップダウ [!UICONTROL Extension] ンを「Adobe Analytics」に、を「に」に設 [!UICONTROL Action Type] 定しま [!UICONTROL Clear Variables]す。

## AppMeasurementのs.clearVars()およびカスタムコードエディターの起動

このメソッドは、Analyticsオブジ `s.clearVars()` ェクトインスタンスをインスタンス化した後、実装の任意の場所で呼び出すことができます。

```js
s.clearVars();
```
