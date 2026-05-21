---
description: 基本的な Report Builder データリクエストを作成する手順です。
title: データリクエストの作成
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
TQID: https://experienceleague.adobe.com/w-oiIfs1qFMoQbaN8YrNIn1TRNHeN97lQOlkLeXdLb0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 284
ht-degree: 50%

---

# Report Builder データリクエストの作成

{{legacy-arb}}

基本的なデータリクエストを作成する手順です。

1. Excel で、「**[!UICONTROL 作成]**」をクリックします。
1. [!UICONTROL リクエストウィザード：ステップ 1] ウィンドウで、[レポートスイート](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)を選択します。
1. （任意）リクエストに適用するセグメントを選択します。 1 つまたは複数のセグメントを選択したら、リストのトップに移動します。

   Report Builder では、Adobe Analytics と同様の方法でセグメントを使用します。 [Analytics セグメントガイド](/help/components/segmentation/seg-home.md)を参照してください。
1. 「[レポートタイプ](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md)」を選択します。
1. 「[日付範囲](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)」を指定してレポートの「[精度](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md)」をクリックします。
1. 「**[!UICONTROL 次へ]**」をクリックします。
1. [レイアウト - リクエストウィザード：ステップ 2](/help/analyze/legacy-report-builder/layout/layout.md) ウィンドウで、レイアウトを選択します。

   | 要素 | 説明 |
   |---|---|
   | ピボットレイアウト | 標準のExcel テーブルと同様に、レイアウト用の行、列、指標グリッドを提供します。 このレイアウトを使用すると、元のリクエスト内に内訳リクエストを追加できます。 |
   | カスタムレイアウト | [!UICONTROL  ピボットレイアウト ]の機能の大部分を提供しますが、グリッド内の各項目をスプレッドシートのどこに配置するかを選択できます。 このレイアウトは、以前のリリースで使用可能な柔軟性を提供します。 |

1. 「[!UICONTROL 指標]」タブで、ツリーの指標をダブルクリックまたはドラッグして、「[!UICONTROL 指標]」グリッドに追加します。
1. 「[!UICONTROL ディメンション]」タブで、ディメンションをダブルクリック（またはドラッグ）して、「[!UICONTROL 行ラベル]」グリッドに追加します。

   手順2で使用可能な[ ディメンション ](/help/analyze/report-builder/filter-dimensions.md)は、手順1で選択した基本レポートと、レポートスイートの設定によって異なります。 ディメンションは、[!UICONTROL  リクエストウィザード：ステップ 1] ウィンドウで選択した元のレポートタイプ指標の関連付け、サブリレーション、または分類である項目です。 ステップ 2で2つ以上のディメンションを追加することは、データリクエストの内訳を作成する方法です。

   詳しくは、[指標とディメンションの追加](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md)を参照してください。
