---
title: clearVars
description: インスタンスオブジェクトの以下の値をクリアします。この関数は要素を削除します（要素を「undefined」に設定します）。
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# clearVars

シングルページアプリケーションなどの実装では、同じページの読み込み時に複数のヒットを送信する必要があります。 このメソッド `clearVars` を使用して、後続のヒットに持続しないように変数値をクリアします。

このメソッドは引数を取らず、値を返しません。 その唯一の目的は、インスタンスオブジェクトから変数の値をクリアすることです。 このメソッドは、次の要素をに設定しま `undefined`す。

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

## Adobe Experience Platform Launchでの変数のクリア

ルールを設定する際に、「変数をクリア」アクションを設定します。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「ルール」タブ [!UICONTROL に移動し] 、目的のルールをクリックします（またはルールを作成します）。
4. 「アク [!UICONTROL ション]」で「+」アイコンをクリックします
5. 「拡張」ド [!UICONTROL ロップダウンを] 「Adobe Analytics」に設定し、「アクシ [!UICONTROL ョンタイプ] 」を「 [!UICONTROL 変数をクリア]」に設定します。

## AppMeasurementおよび起動のカスタムコードエディターのs.clearVars()

Analyticsオブジェクトインスタ `s.clearVars()` ンスをインスタンス化した後、実装の任意の場所でこのメソッドを呼び出すことができます。

```js
s.clearVars();
```
