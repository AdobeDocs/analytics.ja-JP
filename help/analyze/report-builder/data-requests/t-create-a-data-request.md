---
description: 基本的な Report Builder データリクエストを作成する手順です。
title: データリクエストの作成
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
feature: Report Builder
role: 営業者、管理者
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 95%

---


# Report Builder データリクエストの作成

基本的なデータリクエストを作成する手順です。

1. Excel で、「**[!UICONTROL 作成]**」をクリックします。
1. [!UICONTROL リクエストウィザード：ステップ 1] ウィンドウで、[レポートスイート](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を選択します。
1. （オプション）リクエストに適用するセグメントを選択します。1 つまたは複数のセグメントを選択したら、リストのトップに移動します。

   Report Builder では、Adobe Analytics と同様の方法でセグメントを使用します。[Analytics セグメントガイド](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/seg-home.html)を参照してください。1.（オプション）配布に使用する[発行リスト](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md)を選択します。
1. 「[レポートタイプ](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)」を選択します。
1. 「[日付範囲](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)」を指定してレポートの「[精度](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)」をクリックします。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. [レイアウト - リクエストウィザード：ステップ 2](/help/analyze/report-builder/layout/layout.md) ウィンドウで、レイアウトを選択します。

   | 要素 | 説明 |
   |---|---|
   | ピボットレイアウト | Excel の標準的な表と同様に、レイアウトの行、列および指標グリッドを指定できます。このレイアウトを使用すると、オリジナルのリクエストをクロス集計できます。 |
   | カスタムレイアウト | 「[!UICONTROL ピボットレイアウト]」のほとんどの機能を利用できます。ただし、グリッドの各項目をスプレッドシートに配置する場所はユーザーが選択します。このレイアウトは、以前のバージョンで提供されていたもので、柔軟な指定が可能です。 |

1. 「[!UICONTROL 指標]」タブで、ツリーの指標をダブルクリックまたはドラッグして、「[!UICONTROL 指標]」グリッドに追加します。
1. 「[!UICONTROL ディメンション]」タブで、ディメンションをダブルクリック（またはドラッグ）して、「[!UICONTROL 行ラベル]」グリッドに追加します。

   ステップ 2 で使用可能な[ディメンション](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html)は、ステップ 1 で選択したベースレポート、およびレポートスイートの設定によって異なります。相関関係（コリレーション）または下位関係（サブリレーション）が有効化された項目、または[!UICONTROL リクエストウィザード：ステップ 1] ウィンドウで選択したオリジナルレポートのタイプが分類されている場合は分類された項目が使用可能です。ディメンションをクロス集計するには、ステップ 2 で複数のディメンションを追加します。

    [指標およびディメンションの追加](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)を参照してください。
