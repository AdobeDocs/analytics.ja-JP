---
title: サーバー
description: サーバーの名前。
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 92%

---

# サーバー

「サーバー」 [ ディメンション ](overview.md)には、通常、サイトのホスト名が一覧表示されます。 複数のドメインまたはサブドメインを組み合わせたレポートスイートでは、このディメンションは、どのドメインまたはサブドメインのパフォーマンスが最も良いかを調べるのに役立ちます。

このディメンションは、[ページ](page.md)および[サイトセクション](site-section.md)ディメンションに関連しています。 ページの精度は最も高く、サーバーの精度は最も低く、サイトセクションはこの 2 つの間にあります。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`server`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 AppMeasurement は、[`server`](/help/implement/vars/page-vars/server.md) 変数を使用してこのデータを収集します。

## ディメンション項目

ディメンション項目には、サイトのサーバーが含まれます。 組織は、使用する特定のディメンション項目を決定します。 組織によって、`window.location.hostname` 値を使用する場合と、カスタム値を作成する場合があります。 どの方法を使用する場合でも、一貫性があり、[ソリューションデザインドキュメント](/help/implement/prepare/solution-design.md)に記録する必要があります。
