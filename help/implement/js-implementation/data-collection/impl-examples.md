---
description: adobe.com を例として使用します。ここで説明する導入では、同じ visid の cookie を参照します。
keywords: Analytics の導入
seo-description: adobe.com を例として使用します。ここで説明する導入では、同じ visid の cookie を参照します。
seo-title: 実装例
solution: Analytics
title: 実装例
topic: 開発者と導入
uuid: 17d8d2b2-2303-495a- b0f9- d8d3c05f3893
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 実装例

adobe.com を例として使用します。ここで説明する導入では、同じ visid の cookie を参照します。

**Javascript：**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**ハードコーディングされたイメージリクエスト：**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 
```

**AppMeasurement：**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

ファーストパーティ cookie を利用する場合：

**Javascript：**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**ハードコーディングされたイメージリクエスト：**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**AppMeasurement：**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

