---
description: インスタンスオブジェクトの以下の値をクリアします。この関数は要素を削除します（要素を「undefined」に設定します）。
keywords: Analytics Implementation
title: s.clearVars() 関数
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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
>`clearVars()`は、[JavaScript 版 AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) に含まれていますが、H コード以前のバージョンでは使用できません。

