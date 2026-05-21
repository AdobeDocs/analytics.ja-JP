---
title: ページ
description: ページの名前。
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 80%

---

# ページ

「ページ」 [&#x200B; ディメンション &#x200B;](overview.md)には、サイト上のページの名前が一覧表示されます。 これは、Adobe Analytics で最も一般的なディメンションの 1 つで、サイトのどのページのパフォーマンスが最も高いかに関する洞察を提供します。

このディメンションは、[サイトセクション](site-section.md)ディメンションと[サーバー](server.md)ディメンションに関連しています。 ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

このディメンションは、[ページビュー呼び出し（`t()`）](/help/implement/vars/functions/t-method.md) の [`pageName` クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 [リンクトラッキング呼び出し（`tl()`）](/help/implement/vars/functions/tl-method.md)は、`pageName`クエリ文字列が存在する場合でも、常にこのディメンションを削除します。

AppMeasurement は、[`pageName`](/help/implement/vars/page-vars/pagename.md) 変数を使用してこのデータを収集します。 `pageName`変数が設定されていない場合、このディメンションは[`pageURL`](/help/implement/vars/page-vars/pageurl.md)変数を使用してフォールバックします。

## ディメンション項目

ディメンション項目には、サイトのページ名が含まれます。 使用する特定のディメンション項目は、組織によって決まります。 組織によって、`document.title`値を使用する場合と、カスタム値を作成する場合があります。 どの方法を使用する場合でも、一貫性があり、[ソリューションデザイン](/help/implement/prepare/solution-design.md)ドキュメントに記録する必要があります。

>[!NOTE]
>
>Analysis Workspace はデフォルトで最後のアトリビューションを使用し、任意のアトリビューションモデルを使用するオプションがあります。
