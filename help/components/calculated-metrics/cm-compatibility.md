---
description: 「製品の互換性」の 3 つのオプションについて説明します。
title: 指標の互換性
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
TQID: https://experienceleague.adobe.com/nbLLWHYtTLKmGnUxyU2Gp9spVCtE-AZgH2MiXE4nOVY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 57%

---

# 指標の互換性 {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="製品の互換性"
>abstract="使用可能な指標条件の中には、すべての Adobe Analytics ツールと互換性がないものがわずかながらあります。 このリストには、指標と互換性があるツールが示されています。 指標にすべての Adobe Analytics ツールとの互換性を持たせるには、条件を編集してみてください。"

この記事では、3つの製品互換性オプションについて説明します。

計算指標ビルダーで計算指標を作成すると、Adobe Analytics内の1つ以上のツールと互換性があるように指標が表示されます。


| との互換性 | 説明 |
| --- | --- |
| **[!UICONTROL 現在のデータ]** | Adobe Analytics の「[!UICONTROL 現在のデータを含む]」オプションを使用すると、ほとんどの場合、データが完全に処理されてファイナライズされる前に最新の Analytics データを表示できます。 「[!UICONTROL 現在のデータ]」には、ほとんどの指標が数分以内で表示され、迅速な意思決定を可能にする実用的なデータが提供されます。 [!UICONTROL 現在のデータ &#x200B;]は、計算指標（乗算、除算、加算、減算を含むもの）のみをサポートしています。 [!UICONTROL 現在のデータ &#x200B;]は、（セグメントまたは関数を含む）高度な計算指標をサポートしていません。 |
| **[!UICONTROL 完全に処理されたデータ]** | セグメントと分類を含む、完全に処理されたデータ。 データが完全に処理された後、すべての指標を表示する場合は、現在のデータユーザーグループからユーザーを削除して「[!UICONTROL 現在のデータ]」を無効にできます。 |
| **[!UICONTROL マーケティングチャネルレポート]** | ファーストタッチ割り当ての指標は、マーケティングチャネルレポートとのみ互換性があります。 |
