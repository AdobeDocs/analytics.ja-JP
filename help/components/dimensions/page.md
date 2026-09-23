---
title: ページ
description: ページの名前。
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
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
source-wordcount: '226'
ht-degree: 54%
---
# ページ

「ページ」 [&#x200B; ディメンション &#x200B;](overview.md)には、サイト上のページの名前が一覧表示されます。 これは、Adobe Analytics で最も一般的なディメンションの 1 つで、サイトのどのページのパフォーマンスが最も高いかに関するインサイトを提供します。

このディメンションは、[サイトセクション](site-section.md)ディメンションと[サーバー](server.md)ディメンションに関連しています。 ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

[&#x200B; ページビュー呼び出し（`t()`） &#x200B;](/help/implement/vars/functions/t-method.md)で[`pageName`](/help/implement/vars/page-vars/pagename.md)変数を設定します。 `pageName`変数が設定されていない場合、このディメンションは[`pageURL`](/help/implement/vars/page-vars/pageurl.md)変数を使用してフォールバックします。 [&#x200B; リンクトラッキング呼び出し（`tl()`） &#x200B;](/help/implement/vars/functions/tl-method.md)は、`pageName`値が存在する場合でも、常にこのディメンションを削除します。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`pageName`](/help/implement/vars/page-vars/pagename.md) |
| **Web SDK / XDM フィールド** | [`web.webPageDetails.name`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **クエリパラメーター** | [`pageName`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<pageName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 100 バイト |
| **永続性** | ヒット |

## ディメンション項目

ディメンション項目には、サイトのページ名が含まれます。 使用する特定のディメンション項目は、組織によって決まります。 組織によって、`document.title`値を使用する場合と、カスタム値を作成する場合があります。 どの方法を使用する場合でも、一貫性があり、[ソリューションデザイン](/help/implement/prepare/solution-design.md)ドキュメントに記録する必要があります。

>[!NOTE]
>
>Analysis Workspace はデフォルトで最後のアトリビューションを使用し、任意のアトリビューションモデルを使用するオプションがあります。
