---
description: Analysis Workspace のディメンションおよびディメンション項目を分類します。
keywords: Analysis Workspace
title: ディメンションの分類
feature: Dimensions
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: ed4d7bb2b3ba290da575ce18fa6ba62d6b2e9751
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 59%

---

# ワークスペースのディメンションの分類

特定のニーズに合わせて様々な方法でデータを分類でき、関連する指標、ディメンション、セグメント、タイムライン、その他の分析分類値を使用するクエリを作成できます。

1. [ フリーフォームテーブル ](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) で、選択した 1 つ以上の行のコンテキストメニューから、「**[!UICONTROL 分類]**![ 山形の右 ](/help/assets/icons/ChevronRight.svg)」を選択します。

   ![ 選択した項目からアラートを作成を示すステップ結果。](assets/breakdown.png)

1. サブメニューから **[!UICONTROL ディメンション]**、**[!UICONTROL 指標]**、**[!UICONTROL セグメント]** または **[!UICONTROL 日付範囲]** を選択し、項目を選択します。 または、「**[!UICONTROL *検索&#x200B;*]**&#x200B;フィールドでコンポーネントを検索します。

選択した期間で、ディメンション項目またはオーディエンスセグメントで指標を分類できます。より詳細なレベルまで、さらに詳しく調べることもできます。

>[!NOTE]
>
>テーブルに表示する分類の数は、200 までに制限されています。この制限は、分類をエクスポートする場合は増加します。

## 位置で分類

デフォルトでは、分類は静的な行項目に固定されています。 例えば、上位 3 つのページディメンション項目（ホームページ、検索結果、チェックアウト）をマーケティングチャネル別に分類するとします。その後、プロジェクトを終了し、2 週間後に戻ります。プロジェクトを再度開くと、トップ 3 ページが変更され、ホームページ、検索結果、チェックアウトがトップ 4 ～ 6 ページになりました。マーケティングチャネルの分類は、現在 4～6 行目ですが、デフォルトでは、ホームページ、検索結果、チェックアウトの下に表示されます。

これに対し **位置で分類** は、上位 3 つのアイテムが何であるかに関係なく、常に分類されます。 例に戻って参照すると、プロジェクトを再度開く際、マーケティングチャネルの分類はテーブルの上位 3 ページに関連付けられます。ホームページ、検索結果、チェックアウトは 4～6 行目に表示されるようになりました。 この設定の設定方法については、[ 行設定 ](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md) を参照してください。



## 分類へのアトリビューションモデルの適用

テーブル内の分類には、任意のアトリビューションモデルを適用することもできます。このアトリビューションモデルは、親列と同じ場合と異なる場合があります。例えば、マーケティングチャネルディメンションで線形の注文件数を分析するものの、チャネル内の特定のトラッキングコードには U 字形の注文件数を適用するといったことができます。分類に適用されたアトリビューションモデルを編集するには、分類モデルにカーソルを合わせて **[!UICONTROL 編集]** を選択します。

![ 分類設定を示す順序アトリビューション比較 ](assets/breakdown-attribution.png)

アトリビューションモデルを分類に適用したり編集したりする際に想定される動作です。

* 他のアトリビューションが存在しないときにアトリビューションを適用すると、そのアトリビューションは列ツリー全体に適用されます。

* アトリビューションが適用された後に分類を追加した場合は、追加された特定の分類に対してデフォルトが使用されます（そのディメンションにデフォルトが設定されている場合）。それ以外の場合は、親列の分類が使用されます。一部のディメンションにはデフォルトの割り当てがあります。例えば、時間ディメンションとリファラーは同一タッチを使用します。製品ディメンションでは、ラストタッチを使用します。他のディメンションにはデフォルトはなく、親列の割り当てが使用されます。

* 列ツリーに既にアトリビューションが存在する場合、アトリビューションの変更は、編集中のアトリビューションにのみ影響します。

>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis WorkspaceのDimension](https://video.tv.adobe.com/v/41372?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの分類 ](https://video.tv.adobe.com/v/327337?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ ディメンションと指標の追加 ](https://video.tv.adobe.com/v/34734?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ フリーフォームテーブルでのディメンションの操作 ](https://video.tv.adobe.com/v/328531?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。


>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dimensionの位置別分類 ](https://video.tv.adobe.com/v/327412?captions=jpn){target="_blank"} を参照してください。


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

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Adding dimensions and metrics to your project in Analysis Workspace](https://video.tv.adobe.com/v/34734?quality=12&learn=on&captions=jpn){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Working with dimensions in a Freeform Table](https://video.tv.adobe.com/v/328531?quality=12&learn=on&captions=jpn){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [dimension breakdowns by position](https://video.tv.adobe.com/v/327412?quality=12&learn=on&captions=jpn){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


-->