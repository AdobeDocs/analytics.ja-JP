---
description: Analytics は訪問ページ番号が 1 であるサーバーコールが実行されるたびに訪問をカウントします。
keywords: Analytics の導入
seo-description: Analytics は訪問ページ番号が 1 であるサーバーコールが実行されるたびに訪問をカウントします。
seo-title: 訪問回数
solution: Analytics
subtopic: 訪問者数
title: 訪問回数
topic: 開発者と導入
uuid: 3035be8f-6adc-45df- a3f2-5de6d3ed99ce
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 訪問回数

>[!IMPORTANT]
>
>デバイス間で訪問者を識別する方法は推奨されなくなりました。[Adobe Experience Cloud Device Co- opのドキュメント](https://marketing.adobe.com/resources/help/en_US/mcdc/)を参照してください。

Analytics は訪問ページ番号が 1 であるサーバーコールが実行されるたびに訪問をカウントします。

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 4 times: at hits 1, 9, 11, and 12. 訪問者数と同様、初回の関連付けの後は、有効な[!UICONTROL 訪問者 ID] の変更によって[!UICONTROL 訪問ページ番号]が 1 にリセットされるので、訪問数は増加しません。
