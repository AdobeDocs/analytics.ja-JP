---
description: 「製品の互換性」の 3 つのオプションについて説明します。
title: 指標の互換性
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 61%

---

# 指標の互換性 {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="製品の互換性"
>abstract="使用可能な指標の条件の中には、必ずしもすべてのAdobe Analytics ツールと互換性を持つものがあるわけではありません。 このリストには、指標と互換性があるツールが示されています。指標にすべての Adobe Analytics ツールとの互換性を持たせるには、条件を編集してみてください。"

この記事では、3 つの製品互換性オプションについて説明します。

計算指標ビルダーで計算指標を作成すると、指標はAdobe Analytics内の 1 つ以上のツールと互換性があるとして表示されます。


| 互換性の対象 | 説明 |
| --- | --- |
| **[!UICONTROL 現在のデータ]** | Adobe Analytics の「[!UICONTROL 現在のデータを含む]」オプションを使用すると、ほとんどの場合、データが完全に処理されてファイナライズされる前に最新の Analytics データを表示できます。「[!UICONTROL 現在のデータ]」には、ほとんどの指標が数分以内で表示され、迅速な意思決定を可能にする実用的なデータが提供されます。[!UICONTROL &#x200B; 現在のデータ &#x200B;] では、計算指標（乗算、除算、加算、減算を含む指標）のみがサポートされます。[!UICONTROL &#x200B; 現在のデータ &#x200B;] では、高度な計算指標（セグメントや関数を含む計算指標）はサポートされません。 |
| **[!UICONTROL 完全処理済みデータ]** | 処理がすべて完了し、セグメントと分類を含むデータです。データが完全に処理された後、すべての指標を表示する場合は、現在のデータユーザーグループからユーザーを削除して「[!UICONTROL 現在のデータ]」を無効にできます。 |
| **[!UICONTROL マーケティングチャネルレポート]** | ファーストタッチ配分を使用する指標は、マーケティングチャネルレポートとのみ互換性があります。 |
