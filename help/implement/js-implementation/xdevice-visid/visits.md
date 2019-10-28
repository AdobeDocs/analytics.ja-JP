---
description: Analytics は訪問ページ番号が 1 であるサーバーコールが実行されるたびに訪問をカウントします。
keywords: Analytics の実装
seo-description: Analytics は訪問ページ番号が 1 であるサーバーコールが実行されるたびに訪問をカウントします。
seo-title: 訪問回数
solution: Analytics
subtopic: 訪問者
title: 訪問回数
topic: 開発者と実装
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 訪問回数

>[!IMPORTANT]
>
>デバイスをまたいで訪問者を識別するこの方法は、非推奨になりました。詳しくは、[Adobe Experience Cloud Device Co-op ドキュメント](https://marketing.adobe.com/resources/help/ja_JP/mcdc/)を参照してください。

Analytics は訪問ページ番号が 1 であるサーバーコールが実行されるたびに訪問をカウントします。

[前述の表](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA)を見ると、これは 4 回（ヒット1、9、11、12）発生しています。訪問者数と同様、初回の関連付けの後は、有効な[!UICONTROL 訪問者 ID] の変更によって[!UICONTROL 訪問ページ番号]が 1 にリセットされるので、訪問数は増加しません。
