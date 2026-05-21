---
title: 入口
description: 訪問の最初の値のインスタンス。
feature: Metrics
exl-id: f5d359ce-e6ac-4f80-a30b-ff78cc5fc8dc
TQID: https://experienceleague.adobe.com/H3LE0wm2uDL3-pILbvOXvccAJQdo5o9X3uHJ4xZe7UU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 89%

---

# 入口

*このヘルプページでは、入口が指標として機能するしくみについて説明します。 入口がディメンションとして機能する方法について詳しくは、[入口ディメンション](../dimensions/entry-dimensions.md)を参照してください。*

「エントリ」 [指標](overview.md)は、特定のディメンション項目が訪問の最初の値としてキャプチャされた回数を示します。 この指標は、サイトでの訪問者の最初のインプレッションについてより詳しく理解したい場合に役立ちます。 ディメンションの最初の値を表示すると、新しい訪問者が得るエクスペリエンスを把握し、最適化するのに役立ちます。

## この指標の計算方法

特定のディメンションに対して、訪問で最初に表示されたディメンション項目を入口として記録します。 1 回の訪問につき、ディメンションごとに 1 つの入口が存在します。 ディメンションが最初に設定されない場合、訪問の最初のヒットとは限りません。 これは訪問ベースの指標です。ディメンション項目と結び付けられると、残りの訪問でもその値が維持されます。

>[!TIP]
>
>この指標を、訪問ごとに設定されるとは限らないディメンションに対して表示する場合、Analysis Workspace で「未指定」ディメンション項目を非表示にできます。 フィルターアイコンをクリックし、「[!UICONTROL 未指定を含む（なし）]」をオフにします。
