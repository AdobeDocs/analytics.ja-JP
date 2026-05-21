---
title: 出口
description: 訪問の最後の値のインスタンス。
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 88%

---

# 出口

*このヘルプページでは、出口が指標として機能するしくみについて説明します。 出口がディメンションとして機能する方法について詳しくは、[出口ディメンション](../dimensions/exit-dimensions.md)を参照してください。*

「離脱」指標[指標](overview.md)は、特定のディメンション項目が訪問の最後の値としてキャプチャされた回数を示します。 この指標は、訪問者がサイトを離れる前に最後に目にしたことをより深く理解したい場合に役立ちます。 ディメンションの最後の値を確認すると、訪問者が離脱する前に得るエクスペリエンスを把握し、最適化するのに役立ちます。

## この指標の計算方法

[訪問](visits.md)が終了したら、最新のディメンション項目を出口として記録します。 1 回の訪問につき、ディメンションごとに 1 つの出口のみが存在します。 以前のヒットでディメンションが設定された場合、訪問の最後のヒットとは限りません。 これは訪問ベースの指標です。 訪問のすべてのヒットに遡って適用されます。

>[!TIP]
>
>この指標を、訪問ごとに設定されるとは限らないディメンションに対して表示する場合、Analysis Workspace で「未指定」ディメンション項目を非表示にできます。 フィルターアイコンをクリックし、「[!UICONTROL 未指定を含む（なし）]」をオフにします。
