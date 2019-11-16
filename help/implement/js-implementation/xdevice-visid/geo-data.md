---
description: 地域特性データは、訪問者の初回ヒットに基づいて記録され、1 回の訪問に対しては使用されるデバイスにかかわらず変更されません。
keywords: Analytics Implementation
solution: Analytics
title: 地域特性データ
topic: Developer and implementation
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 地域特性データ

>[!IMPORTANT]
>
>デバイスをまたいで訪問者を識別するこの方法は、非推奨になりました。詳しくは、 [Adobe Experience Cloud Device Co-opのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

地域特性データは、訪問者の初回ヒットに基づいて記録され、1 回の訪問に対しては使用されるデバイスにかかわらず変更されません。

訪問者が家のコンピューターからサイトを閲覧し、その後 30 分以内にモバイルデバイスからサイトを閲覧した場合、地域特性データは変更されません。VISTA を使用して eVar に地域特性データを設定する場合、この地域データは各ヒットにおける IP アドレスに基づきます。したがって、同じ訪問中に IP アドレスが変更された場合は、地域特性データの値が複数になる可能性があります。
