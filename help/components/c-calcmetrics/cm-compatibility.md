---
description: 「製品の互換性」の 3 つのオプションについて説明します。
title: 指標の互換性
feature: Calculated Metrics
exl-id: 936d8139-7bbc-4de4-9e30-60ef5e12be08
source-git-commit: d9f95b12a43305cecff1190e6544334f3b48835d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 50%

---

# 指標の互換性 {#metrics-compatibility}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_productcompatibility"
>title="製品の互換性"
>abstract="「使用可能な指標条件の中には、必ずしもすべてのAdobe Analytics ツールと互換性を持つものがありません。 このリストには、指標と互換性のあるツールが示されています。 指標にすべてのAdobe Analytics ツールとの互換性を持たせるには、条件を編集してみてください。"

この記事では、3 つの製品互換性オプションについて説明します。

計算指標ビルダーで計算指標を作成すると、指標はAdobe Analytics内の 1 つ以上のツールと互換性があるとして表示されます。 例えば、Analysis Workspace、Reports &amp; Analytics、Data Warehouseなどです。


| 互換性の対象 | 説明 |
| --- | --- |
| 現在のデータ | Adobe Analytics の「[!UICONTROL 現在のデータを含む]」オプションを使用すると、ほとんどの場合、データが完全に処理されてファイナライズされる前に最新の Analytics データを表示できます。「[!UICONTROL 現在のデータ]」には、ほとんどの指標が数分以内で表示され、迅速な意思決定を可能にする実用的なデータが提供されます。[!UICONTROL  現在のデータ ] では、計算指標（乗算、除算、加算、減算を含む指標）のみがサポートされます。[!UICONTROL  現在のデータ ] では、高度な計算指標（セグメントや関数を含む計算指標）はサポートされません。 |
| 処理済みのデータ | 処理がすべて完了し、セグメントと分類を含むデータです。データが完全に処理された後、すべての指標を表示する場合は、現在のデータユーザーグループからユーザーを削除して「[!UICONTROL 現在のデータ]」を無効にできます。 |
| マーケティングチャネルレポート | ファーストタッチ配分を使用する指標は、マーケティングチャネルレポートとのみ互換性があります。 |
