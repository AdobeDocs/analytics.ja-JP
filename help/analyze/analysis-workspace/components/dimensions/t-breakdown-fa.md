---
description: Analysis Workspaceでディメンションとディメンション項目を分割する方法について説明します。
keywords: Analysis Workspace
title: ディメンションの分類
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
TQID: https://experienceleague.adobe.com/GJZSzrey1b6zlmZzO9weS-BimDXtIuWcBV4L6zJEoiY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 58%

---

# ディメンションの分類

Analysis Workspaceでは、適切な指標やディメンション、セグメント、タイムラインなどの分析ブレークダウン値を使用してクエリを構築し、特定のニーズに合わせて無制限にデータを分類できます。

1. [&#x200B; フリーフォームテーブル &#x200B;](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md)で、選択した1つ以上の行のコンテキストメニューから、**[!UICONTROL 分類]** ![&#x200B; シェブロン右](/help/assets/icons/ChevronRight.svg)を選択します。

   ![選択範囲からアラートを作成を表示する手順の結果。](assets/breakdown.png)

1. サブメニューから、**[!UICONTROL ディメンション]**、**[!UICONTROL 指標]**、**[!UICONTROL セグメント]**&#x200B;または&#x200B;**[!UICONTROL 日付範囲]**&#x200B;を選択し、項目を選択します。 または、**[!UICONTROL *検索&#x200B;*]**&#x200B;フィールドでコンポーネントを検索します。

選択した期間で、ディメンション項目またはオーディエンスセグメントで指標を分類できます。 より詳細なレベルまで、さらに詳しく調べることもできます。

>[!NOTE]
>
>テーブルに表示する分類の数は、200 までに制限されています。 この制限は、分類をエクスポートする場合は増加します。

## 位置で分類

デフォルトでは、分類は静的な行アイテムに固定されています。 例えば、上位 3 つのページディメンション項目（ホームページ、検索結果、チェックアウト）をマーケティングチャネル別に分類するとします。 その後、プロジェクトを終了し、2 週間後に戻ります。 プロジェクトを再度開くと、トップ 3 ページが変更され、ホームページ、検索結果、チェックアウトがトップ 4 ～ 6 ページになりました。 デフォルトでは、マーケティングチャネルの分類は、現在は 4～6 行になっているにもかかわらず、ホームページ、検索結果、チェックアウトの下に引き続き表示されます。

対照的に、**位置による分類**&#x200B;は、これらの項目が何であるかに関係なく、常に上位3つの項目を分類します。 例に戻って参照すると、プロジェクトを再度開く際、マーケティングチャネルの分類はテーブルの上位 3 ページに関連付けられます。 また、現在、4～6 行になっているホームページ、検索結果、チェックアウトには関連付けられません。 この設定の設定方法については、[行の設定](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)を参照してください。



## 分類へのアトリビューションモデルの適用

テーブル内の分類には、任意のアトリビューションモデルを適用することもできます。 このアトリビューションモデルは、親列と同じ場合と異なる場合があります。 例えば、マーケティングチャネルディメンションで線形の注文件数を分析するものの、チャネル内の特定のトラッキングコードには U 字形の注文件数を適用するといったことができます。 分類に適用されたアトリビューションモデルを編集するには、分類モデルにカーソルを合わせて、**[!UICONTROL 編集]**&#x200B;を選択します。

![分類の設定を示す注文属性比較](assets/breakdown-attribution.png)

アトリビューションモデルを分類に適用したり編集したりする際に想定される動作です。

* 他のアトリビューションが存在しないときにアトリビューションを適用すると、そのアトリビューションは列ツリー全体に適用されます。

* アトリビューションが適用された後に分類を追加した場合は、追加された特定の分類に対してデフォルトが使用されます（そのディメンションにデフォルトが設定されている場合）。 それ以外の場合は、親列の分類が使用されます。 一部のディメンションにはデフォルトの割り当てがあります。 例えば、時間ディメンションとリファラーは同一タッチを使用します。 製品ディメンションでは、ラストタッチを使用します。 他のディメンションにはデフォルトはなく、親列の割り当てが使用されます。

* 列ツリーに既にアトリビューションが存在する場合、アトリビューションの変更は、編集中のアトリビューションにのみ影響します。

>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis WorkspaceのDimension](https://video.tv.adobe.com/v/41372?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの内訳](https://video.tv.adobe.com/v/327337?captions=jpn&quality=12&learn=on){target="_blank"}を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [&#x200B; ディメンションと指標の追加](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"}を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [&#x200B; フリーフォームテーブルでのディメンションの操作](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table){target="_blank"}を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの位置別の内訳](https://video.tv.adobe.com/v/327412?captions=jpn){target="_blank"}を参照してください。


>[!ENDSHADEBOX]



<!--
# Break down dimensions

Break down dimensions and dimension items in Analysis Workspace.

Break down your data in unlimited ways for your specific needs; build queries using relevant metrics, dimensions, segments, time lines, and other analysis breakdown values.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table.
1. In the data table, right-click a line item and select **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Step Result](assets/fa_data_table_actions.png)

   You can break down metrics by dimension items or audience segments across selected time periods. You can also drill down further to a more granular level.

   >[!NOTE]
   >
   >The number of breakdowns to show in the table is limited to 200. This limit will increase for exporting breakdowns.

## Apply attribution models to breakdowns

Any breakdown within a table can also have any attribution model applied to it. This attribution model can be the same or different from the parent column. For example, you can analyze linear Orders on your Marketing Channels dimension but apply U-Shaped Orders to the specific tracking codes within a Channel. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Breakdown settings](assets/breakdown_settings.png)

This is the expected behavior when applying attribution models to breakdowns or editing them:

* If you apply an attribution when no other attributions exist, then the attribution applies to the entire column tree.

* If you add a breakdown after an attribution has been applied, it will use the default for the given breakdown that was added, if that dimension has a default. Otherwise it will use the breakdown from the parent column. Some dimensions have a default allocation.  For example, [!UICONTROL Time] dimensions and [!UICONTROL Referrer] use [!UICONTROL Same Touch]. The [!UICONTROL Product] dimension uses [!UICONTROL Last Touch]. Other dimensions don't have a default, and will use the parent column allocation.

* If there are already attributions in the column tree, changing the attribution only impacts the one you are editing.

## Videos


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding dimensions and metrics to your project in Analysis Workspace](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/dimensions/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Working with dimensions in a Freeform Table](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimension breakdowns by position](https://video.tv.adobe.com/v/327412?captions=jpn&quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


-->