---
description: シンプルな計算指標の作成方法を説明します。
title: シンプルな計算指標の作成
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 0fbd80070051286f999af8eec9100f617cc498d5
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 17%

---

# シンプルな計算指標の作成

次の情報では、シンプルな *訪問あたりのページビュー数* 指標の作成方法を説明します。

1. [&#x200B; 指標の作成 &#x200B;](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md) の説明に従って、指標の作成を開始します。
1. 指標に `Page Views per Visit` などの名前を付けます。
1. 指標の使用目的を示すために、指標にわかりやすい **[!UICONTROL 説明]** を指定します。
1. 右側の **[!UICONTROL 形式]** を選択します。 この例では、「**[!UICONTROL 小数]** を選択します。
1. レポートに表示する小数点以下の桁数を指定します。
1. **[!UICONTROL 更新方向のトレンドの表示方法]** ドロップダウンメニューで、「▲**[!UICONTROL 良（緑）]**」を選択します。
1. **[!UICONTROL タグ]**&#x200B;を追加して指標を管理します。
1. この計算指標については、まず **[!UICONTROL 指標]** コンポーネントからキャンバスの **[!UICONTROL 定義]** セクションに **[!UICONTROL ページビュー]** をドラッグします。
1. 次に、**[!UICONTROL 指標]** コンポーネントから **[!UICONTROL 訪問回数]** をドラッグし、**[!UICONTROL ページビュー数]** の下の指標をドロップします（青い線が表示されるまで待ってから指標をドロップします）。
1. 除算 ![&#x200B; 除算 &#x200B;](/help/assets/icons/Divide.svg) 演算子を選択します。 （除算がデフォルトの演算子です）。
1. 指標の作成中に、指標の **[!UICONTROL プレビュー]** を表示できます。
1. [&#x200B; 製品の互換性 &#x200B;](/help/components/calculated-metrics/cm-compatibility.md) は、指標が「現在のデータ」と互換性があるか、「完全に処理されたデータ」のみと互換性があるかを示します。

   ![&#x200B; 簡易計算指標 &#x200B;](assets/simple-calculated-metric.png)
1. 「**[!UICONTROL 保存]**」を選択します。

   「**[!UICONTROL 概要]**」の数式は、指標の定義を変更すると更新されます。

1. （任意）指標の共有、承認、（再）タグ付け、名前変更、削除を行うには、[&#x200B; 計算指標マネージャー &#x200B;](/help/components/calculated-metrics/workflow/cm-manager.md) に移動します。

