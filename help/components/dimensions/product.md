---
title: 製品
description: 製品名。
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 58%
---
# 製品

「製品」 [&#x200B; ディメンション &#x200B;](overview.md)は、ヒット内の製品の名前を報告します。 これは、`products` 変数を使用し、トップセラーや最も多く閲覧された製品に関する指標を確認したい場合に便利です。 サイトに製品が存在しない場合、このディメンションは意図的に空白にする可能性があります。

## このディメンションへのデータ入力

このディメンションは、最初と2番目のセミコロン （`;`）の間の文字列である[`products`](/help/implement/vars/page-vars/products.md)変数の製品名を参照しています。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Web SDK / XDM フィールド** | [`productListItems[].name`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **クエリパラメーター** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 100 バイト |
| **永続性** | ヒット |

## ディメンション項目

この変数は、実装内のカスタム文字列に基づくので、組織でディメンション項目が何かを決定します。 製品に対して一貫した命名規則を設定することをお勧めします。 [分類](../classifications/classifications-overview.md)は、別の方法で製品をグループ化したり、わかりやすい名前を付けたりする場合に利用できます。 「製品」ディメンションと「カテゴリ」ディメンションの両方を使用することをお勧めします。
