---
description: 指定の訪問者 ID Cookie に対して関連付けが発生した場合はいつでもセグメントを作成できます。
keywords: Analytics の実装
seo-description: 指定の訪問者 ID Cookie に対して関連付けが発生した場合はいつでもセグメントを作成できます。
seo-title: セグメントの作成
solution: Analytics
title: セグメントの作成
topic: 開発者と実装
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# セグメントの作成

>[!IMPORTANT]
>
>デバイスをまたいで訪問者を識別するこの方法は、非推奨になりました。詳しくは、[Adobe Experience Cloud Device Co-op ドキュメント](https://marketing.adobe.com/resources/help/ja_JP/mcdc/)を参照してください。

指定の訪問者 ID Cookie に対して関連付けが発生した場合はいつでもセグメントを作成できます。

[前述の表](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA)に基づいて、訪問回数が 9 のセグメントを作成した場合は、サーバーコール 12 および 13 が含まれます。サーバーコール 11 が理論的には同じ訪問の一部であっても、そのサーバーコールの過去データは変更されず、訪問回数も変化しません。
