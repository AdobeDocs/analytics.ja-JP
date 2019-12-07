---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# trackingServer

 変数は、イメージリクエストと cookie が書き込まれているドメインを指定するために、ファーストパーティ cookie の導入に使用されます。


<!-- 

trackingServer.xml

 -->

セキュリティ保護されていないページで使用されます。if *`trackingServer`* が定義されている場合、2o7.net には何も送信されません。*`trackingServer`* が定義されていない（および dc が定義されていない）場合、データは 112.2o7.net に送信されます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | "" |

アドビのデータセンターのリストについては、[ここ](https://helpx.adobe.com/analytics/kb/determining-data-center.html)を参照してください。