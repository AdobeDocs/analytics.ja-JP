---
title: サイトセクション
description: サイトセクションの名前。
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
TQID: https://experienceleague.adobe.com/fZwN-24--98XULDEgHR-5dcIsiYXspaSOsv1t-M0iys
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 66%
---
# サイトセクション

「サイトセクション」 [ ディメンション ](overview.md)には、サイト上のサイトセクションの名前が一覧表示されます。 大規模なサイトでは、ページをセクションにグループ化すると便利です。 このディメンションは、最も多く閲覧されたサイトセクションやパフォーマンスの高いサイトセクションを確認するのに役立ちます。

このディメンションは、[ページ](page.md)ディメンションと[サーバー](server.md)ディメンションに関連しています。 ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

AppMeasurement は、[`channel`](/help/implement/vars/page-vars/channel.md) 変数を使用してこのデータを収集します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`channel`](/help/implement/vars/page-vars/channel.md) |
| **Web SDK / XDM フィールド** | [`web.webPageDetails.siteSection`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **クエリパラメーター** | [`ch`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<channel>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 100 バイト |
| **永続性** | ヒット |

## ディメンション項目

ディメンション項目には、サイトのサイトセクションの名前が含まれます。 使用する具体的なディメンション項目は、組織側で決定します。 どの方法を使用する場合でも、一貫性があり、[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)に記録する必要があります。
