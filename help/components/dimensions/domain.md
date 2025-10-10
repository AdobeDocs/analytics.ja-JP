---
title: ドメイン
description: 訪問者がインターネットにアクセスするために使用する組織または ISP。
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 52%

---

# ドメイン

「ドメイン [&#x200B; ディメンション &#x200B;](overview.md) は、訪問者がインターネットへのアクセスに使用するアクセスポイントをレポートします。

## このディメンションへのデータ入力

アドビは、 [Digital Element](https://www.digitalelement.com/) と提携して、アクセスポイントのドメインを判断しています。 アクセスポイントドメインを判断する際には、DNS 逆引き参照を含むいくつかのメソッドを使用します。 設定は必要なく、入力する変数はありません。

* AppMeasurement実装の場合、このディメンションは初期設定の状態で動作します。
* Web SDK実装の場合、「データストリームの設定 [!UICONTROL &#x200B; 時に &#x200B;] ネットワーク検索 [&#x200B; を有効に &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja) ます。

## ディメンション項目

ディメンション項目の例としては、`comcast.net`、`rr.com`、`sbcglobal.net`、`amazonaws.com` などがあります。これらのドメインはアクセスポイントであり、必ずしも ISP または組織を表すドメインではありません。

ディメンション値が `None` の場合は、アクセスポイントの IP アドレスの所有者がドメインを提供しなかったことを意味します。
