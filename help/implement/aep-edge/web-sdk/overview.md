---
title: Adobe Experience Platform Web SDK を使用したAdobe Analyticsの実装
description: Adobe Experience Platformデータ収集の Web SDK 拡張機能を使用して、Adobe Analyticsにデータを送信します。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 33%

---


# Adobe Experience Platform Web SDK を使用したAdobe Analyticsの実装

以下を使用して、 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=ja) をクリックしてAdobe Analyticsにデータを送信します。 この実装方法は、 [エクスペリエンスデータモデル (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja) を Analytics で使用される形式に変換します。

## セットアップ

XDM データを受信する Analytics を設定するには、次の手順を実行します。

1. [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja) をインストールして[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)します。

1. 該当するレポートスイートが目的のデータにマッピングされていることを確認します。 XDM データは、Adobe Experience Edge から自動的にレポートスイートに送られます。
