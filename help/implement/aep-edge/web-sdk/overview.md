---
title: Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装
description: Adobe Experience Platform データ収集の Web SDK 拡張機能を使用して、Adobe Analytics にデータを送信します。
exl-id: 97f8d650-247f-4386-b4d2-699f3dab0467
source-git-commit: 72b2497c5060f2309f2232a09e46166ac63da944
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---

# Adobe Experience Platform Web SDK を使用した Adobe Analytics の実装

[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=ja) を使用して、データを Adobe Analytics に送信できます。この実装を機能させるには、[Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を Analytics で使用される形式に変換します。

## セットアップ

XDM データを受信する Analytics を設定するには、次の手順を実行します。

1. [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=ja) をインストールして[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)します。

1. 該当するレポートスイートが目的のデータにマッピングされていることを確認します。XDM データは、Adobe Experience Edge から自動的にレポートスイートへ送られます。
