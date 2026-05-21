---
description: Analysis Workspaceでディメンションの詳細と最上位の値を表示する方法について説明します。
title: プレビューディメンション
feature: Dimensions
role: User, Admin
exl-id: 897edc76-6744-4d8c-ab0e-20672838f7b3
TQID: https://experienceleague.adobe.com/2pgnWuCqEPdp8Uod5cFBzgLBYkUCRqksNJrLanpurkE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 4%

---

# ディメンションのプレビュー

コンポーネントの[&#x200B; コンポーネント情報](/help/analyze/analysis-workspace/components/use-components-in-workspace.md#component-info)を使用して、ディメンションの上位アイテムを表示できます。

![&#x200B; コンポーネント情報](assets/component-info.png)

<!--
Now, by default, we show dynamic values instead of static ones, with the option to turn them into static values. Other things to note:

* As your data updates, the dynamic dimension columns will update to show the current 5/15 dimension items.
* A dynamic dimension column that is copied or moved will become static.
* When hovering a static dimension column you will see a lock icon, indicating that the dimension is static.

![Dimension column popup highlighting the lock icon.](assets/dimension_static.png)

-->


## ディメンション項目の表示

コンポーネントパネルでディメンションの![ChevronRight](/help/assets/icons/ChevronRight.svg)を選択すると、ディメンション項目のリストが表示されます。 通常、ディメンション項目のリストには、過去30日間の上位の項目が表示されます。 より多くの項目が使用可能な場合、パネルで選択した日付範囲の外で、リンクを選択して他の項目を表示します。 例えば、**[!UICONTROL 先月]**&#x200B;の項目を表示します。

![&#x200B; ディメンション項目を表示](assets/dimension-items.png)


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
