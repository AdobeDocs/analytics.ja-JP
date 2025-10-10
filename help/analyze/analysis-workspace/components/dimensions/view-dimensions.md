---
description: Analysis Workspaceでディメンションの詳細と上位の値を表示する方法について説明します。
title: 寸法をプレビュー
feature: Dimensions
role: User, Admin
exl-id: 897edc76-6744-4d8c-ab0e-20672838f7b3
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 4%

---

# ディメンションのプレビュー

コンポーネントに [&#x200B; コンポーネント情報 &#x200B;](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info) を使用して、ディメンションの上位項目を表示できます。

![&#x200B; コンポーネント情報 &#x200B;](assets/component-info.png)

<!--
Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![Dimension column popup highlighting the lock icon.](assets/dimension_static.png)

-->


## ディメンション項目の表示

コンポーネントパネルのディメンションに対して ![ChevronRight](/help/assets/icons/ChevronRight.svg) を選択すると、そのディメンション項目のリストが表示されます。 ディメンション項目のリストには、通常、過去 30 日間の上位の項目が表示されます。 使用可能な項目が他にもある場合は、パネルで選択した日付範囲外にあるリンクを選択すると、さらに多くの項目が表示されます。 例：**[!UICONTROL 先月の項目を表示]**

![&#x200B; ディメンション項目を表示 &#x200B;](assets/dimension-items.png)


<!--
# Preview dimensions

Hover over the information (i) icon next to a dimension. This shows the top 5 values for non-time dimensions (and 15 for time dimensions). We used to keep those values static (i.e., the 5 values picked never changed).

![](assets/dimension-preview.png)

Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![](assets/dimension_static.png)

## Show dimension items

When you hover over a dimension and click the grey right-arrow next to it, a list of its dimension items appears. Any list of dimension items usually shows the top items for the last 30 days.

If you scroll down to the bottom of the list, you see **[!UICONTROL Show Top Items From Last 18 Months]**. Click this option to see top dimension items from the last 547 days.

-->
