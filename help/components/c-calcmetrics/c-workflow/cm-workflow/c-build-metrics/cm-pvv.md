---
description: シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。
title: シンプルな「訪問あたりのページビュー数」指標の作成
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 56%

---

# 「訪問あたりのページビュー数」指標の作成

次の情報では、シンプルな「訪問あたりのページビュー数」指標の作成方法を説明します。

シンプルな「訪問あたりのページビュー数」指標を作成するには：

1. 指標の作成を開始します。詳しくは、[ 指標の作成 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) を参照してください。
1. 指標に「訪問あたりのページビュー数」などの名前を付けます。
1. ユーザーにわかりやすい指標の用途を「**[!UICONTROL 説明]**」に入力します。
1. 右側の **[!UICONTROL 形式]** を選択します。 この例では、「[!UICONTROL **小数**] を選択します。
1. レポートに表示する小数点以下の桁数を指定します。
1. [!UICONTROL **更新方向のトレンドを次の形式で表示**] ドロップダウンメニューで [!UICONTROL **良好（緑）**] を選択します。
1. **[!UICONTROL タグ]**&#x200B;を追加して指標を管理します。
1. この指標では、まずページビューをキャンバスの [!UICONTROL **定義**] セクションにドラッグしてから、その下の訪問回数をドラッグします（青い線が表示されるまで待ってからドロップします）。
1. 除算演算子を選択します（除算がデフォルトの演算子です）。
1. これで、指標の作成時に、その指標の&#x200B;**[!UICONTROL プレビュー]**&#x200B;を右上に表示できます。
1. 製品の互換性は、指標が「[現在のデータ](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=ja)」と互換性があるかどうか、または「処理済みのデータ」とのみ互換性があるかどうかを示します。
1. 「**[!UICONTROL 保存]**」を選択します。

   「**[!UICONTROL 概要]**」の数式は、指標の定義を変更すると更新されます。

1. （任意）指標の共有、承認、（再）タグ付け、名前変更、削除を行うには、[ 計算指標 ](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md) ページに移動します。
