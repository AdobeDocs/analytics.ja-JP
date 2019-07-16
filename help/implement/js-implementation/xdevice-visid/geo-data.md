---
description: 地域特性データは、訪問者の初回ヒットに基づいて記録され、1 回の訪問に対しては使用されるデバイスにかかわらず変更されません。
keywords: Analytics の導入
seo-description: 地域特性データは、訪問者の初回ヒットに基づいて記録され、1 回の訪問に対しては使用されるデバイスにかかわらず変更されません。
seo-title: 地域特性データ
solution: Analytics
title: 地域特性データ
topic: 開発者と導入
uuid: 8449bf11- c367-4698- a73e- f6cb59f8c945
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 地域特性データ

>[!IMPORTANT]
>
>デバイス間で訪問者を識別する方法は推奨されなくなりました。[Adobe Experience Cloud Device Co- opのドキュメント](https://marketing.adobe.com/resources/help/en_US/mcdc/)を参照してください。

地域特性データは、訪問者の初回ヒットに基づいて記録され、1 回の訪問に対しては使用されるデバイスにかかわらず変更されません。

訪問者が家のコンピューターからサイトを閲覧し、その後 30 分以内にモバイルデバイスからサイトを閲覧した場合、地域特性データは変更されません。VISTAを使用してeVarに地域特性データを入力する場合、各ヒットのIPアドレスに基づきます。これにより、同じ訪問に対してIPアドレスが変更された場合に、地域特性データの値が複数になる可能性があります。
