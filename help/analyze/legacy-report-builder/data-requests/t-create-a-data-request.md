---
description: 基本的な Report Builder データリクエストを作成する手順です。
title: データリクエストの作成
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 96%

---

# Report Builder データリクエストの作成

{{legacy-arb}}

基本的なデータリクエストを作成する手順です。

1. Excel で、「**[!UICONTROL 作成]**」をクリックします。
1. [!UICONTROL リクエストウィザード：ステップ 1] ウィンドウで、[レポートスイート](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を選択します。
1. （任意）リクエストに適用するセグメントを選択します。1 つまたは複数のセグメントを選択したら、リストのトップに移動します。

   Report Builder では、Adobe Analytics と同様の方法でセグメントを使用します。[Analytics セグメントガイド](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=ja)を参照してください。
1. 「[レポートタイプ](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)」を選択します。
1. 「[日付範囲](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)」を指定してレポートの「[精度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)」をクリックします。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. [レイアウト - リクエストウィザード：ステップ 2](/help/analyze/legacy-report-builder/layout/layout.md) ウィンドウで、レイアウトを選択します。

   | 要素 | 説明 |
   |---|---|
   | ピボットレイアウト | Excel の標準的な表と同様に、レイアウトの行、列および指標グリッドを指定できます。このレイアウトを使用すると、オリジナルのリクエストをクロス集計できます。 |
   | カスタムレイアウト | 「[!UICONTROL ピボットレイアウト]」のほとんどの機能を利用できます。ただし、グリッドの各項目をスプレッドシートに配置する場所はユーザーが選択します。このレイアウトは、以前のバージョンで提供されていたもので、柔軟な指定が可能です。 |

1. 「[!UICONTROL 指標]」タブで、ツリーの指標をダブルクリックまたはドラッグして、「[!UICONTROL 指標]」グリッドに追加します。
1. 「[!UICONTROL ディメンション]」タブで、ディメンションをダブルクリック（またはドラッグ）して、「[!UICONTROL 行ラベル]」グリッドに追加します。

   ステップ 2 で使用可能な[ディメンション](https://experienceleague.adobe.com/docs/analytics/analyze/legacy-report-builder/layout/filter-dimenson/filter-dimensions.html?lang=ja)は、ステップ 1 で選択したベースレポート、およびレポートスイートの設定によって異なります。相関関係（コリレーション）または下位関係（サブリレーション）が有効化された項目、または[!UICONTROL リクエストウィザード：ステップ 1] ウィンドウで選択したオリジナルレポートのタイプが分類されている場合は分類された項目が使用可能です。ディメンションをクロス集計するには、ステップ 2 で複数のディメンションを追加します。

   詳しくは、[ 指標およびDimensionの追加 ](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) を参照してください。
