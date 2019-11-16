---
description: Analytics は、一意の有効な各訪問者 IDを一意の訪問者としてカウントします。
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: 訪問者
topic: Developer and implementation
uuid: 16cfdb64-a3c6-4056-97da-3227cddcf1cd
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 訪問者

>[!IMPORTANT]
>
>デバイスをまたいで訪問者を識別するこの方法は、非推奨になりました。詳しくは、 [Adobe Experience Cloud Device Co-opのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/mcdc/)。

Analytics は、一意の有効な各訪問者 IDを一意の訪問者としてカウントします。

[前述の表](/help/implement/js-implementation/xdevice-visid/visit-example.md)を見ると、これは 3 回（ヒット1、9、10）発生しています。サーバーコールで有効な[!UICONTROL 訪問者 ID] が同じ場合、追加の訪問者はカウントされません。また、この訪問の間隔が数時間あったり、異なるデバイスからの訪問であっても、訪問者 ID が同じなので、訪問者は増えません。

このような場合、クロスデバイス訪問者の識別を有効にすると、一意の訪問者の数が増加することがあります。訪問者が、同じ訪問で 2 回カウントされる可能性があるためです。初回訪問で 1 回カウントされ、ユーザーが認証された後でもう 1 回カウントされます。

新しい訪問者がサイトを表示すると、`s_vi` cookie が設定および保存されます。データ収集サーバーでは、新しい訪問者プロファイルがこの訪問者 ID に対して作成され、cookie に設定された訪問者 ID が有効な[!UICONTROL 訪問者 ID] として設定されます。

デバイス間の訪問者の識別を有効にすると、（例えば認証後などに）後続のヒットで[!UICONTROL 訪問者 ID] 変数が提供された場合、その ID が有効な[!UICONTROL 訪問者 ID] になります。これにより、有効な[!UICONTROL 訪問者 ID] が認証の直後に変更されるので、訪問者が複数回カウントされることになります。

![](assets/visitors.png)

初回の関連付けの後は、訪問者は[!UICONTROL 訪問者 ID] cookie によって関連付けられるので、訪問数は増加しません。訪問者が後でサイトを表示し認証した場合も、有効な[!UICONTROL 訪問者 ID] は認証後に変更されないので、訪問者数は水増しされません。

![](assets/visitors_2.png)

