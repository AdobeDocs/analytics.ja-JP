---
description: インスタンスオブジェクトの以下の値をクリアします。この関数は要素を削除します（要素を「undefined」に設定します）。
keywords: Analytics の導入
seo-description: インスタンスオブジェクトの以下の値をクリアします。この関数は要素を削除します（要素を「undefined」に設定します）。
seo-title: s.clearVars() 関数
solution: Analytics
title: s.clearVars() 関数
topic: 開発者と導入
uuid: 43c425bc-15ae-4892- a5a5- e1defcb25ff4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# s.clearVars() 関数

インスタンスオブジェクトの以下の値をクリアします。この関数は要素を削除します（要素を「undefined」に設定します）。

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

次に例を示します。

```js
s.clearVars()
```

>[!NOTE]
>
>`clearVars()` はJavaScript版 [AppMeasurementに含まれています](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) が、Hコードおよび以前のバージョンでは使用できません。

