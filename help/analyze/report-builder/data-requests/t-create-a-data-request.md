---
description: Report Builderの基本的なデータリクエストを作成する手順です。
seo-description: Report Builderの基本的なデータリクエストを作成する手順です。
seo-title: Report Builderデータリクエストの作成
solution: Analytics
title: データリクエストの作成
topic: Report Builder
uuid: 5d0151f1- e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 65b3c25288060b1b6d0b9590a8fdca4087f416a0

---


# Report Builderデータリクエストの作成

基本的なデータリクエストを作成する手順です。

1. In Excel, click **[!UICONTROL Create]**.
1. [!UICONTROL リクエストウィザード:ステップ1] ウィンドウで、 [レポートスイートを選択](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913)します。
1. （オプション）リクエストに適用するセグメントを選択します。1 つまたは複数のセグメントを選択したら、リストのトップに移動します。

   Report Builder では、Adobe Analytics と同様の方法でセグメントを使用します。[Analytics セグメントガイド](https://marketing.adobe.com/resources/help/en_US/analytics/segment/)を参照してください。1. (Optional) Select a [publishing list](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C) to use for distribution.
1. [レポートタイプ](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC)を選択します。
1. [日付範囲](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) とレポート [精度](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB)を指定します。
1. Click **[!UICONTROL Next]**.
1. [レイアウト-リクエストウィザード:ステップ2](../../../analyze/report-builder/layout/layout.md#concept_D66E1C2217E24E1F837AC064C61919DB) ウィンドウで、レイアウトを指定します。

   | 要素 | 説明 |
   |---|---|
   | ピボットレイアウト | Excel の標準的な表と同様に、レイアウトの行、列および指標グリッドを指定できます。このレイアウトを使用すると、オリジナルのリクエストをクロス集計できます。 |
   | カスタムレイアウト | 「[!UICONTROL ピボットレイアウト]」のほとんどの機能を利用できます。ただし、グリッドの各項目をスプレッドシートに配置する場所はユーザーが選択します。このレイアウトは、以前のバージョンで提供されていたもので、柔軟な指定が可能です。 |

1. 「[!UICONTROL 指標]」タブで、ツリーの指標をダブルクリックまたはドラッグして、「[!UICONTROL 指標]」グリッドに追加します。
1. 「[!UICONTROL ディメンション]」タブで、ディメンションをダブルクリック（またはドラッグ）して、「[!UICONTROL 行ラベル]」グリッドに追加します。

   ステップ 2 で使用可能な[ディメンション](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=dimensions)は、ステップ 1 で選択したベースレポート、およびレポートスイートの設定によって異なります。相関関係（コリレーション）または下位関係（サブリレーション）が有効化された項目、または[!UICONTROL リクエストウィザード：ステップ 1] ウィンドウで選択したオリジナルレポートのタイプが分類されている場合は分類された項目が使用可能です。ディメンションをクロス集計するには、ステップ 2 で複数のディメンションを追加します。

   詳しくは、[指標およびディメンションの追加](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4)を参照してください。