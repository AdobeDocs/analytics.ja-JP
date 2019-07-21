---
description: シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。
seo-description: シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。
seo-title: 単純な「訪問あたりのページビュー数」指標の作成
title: 単純な「訪問あたりのページビュー数」指標の作成
uuid: 0730e51c-1f8f-473b-8825- d72911f2944c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 単純な「訪問あたりのページビュー数」指標の作成

シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。

UI コンポーネントについて詳しくは、「 [指標の作成](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md#concept_5EC82A91EB9C44FC870326C85F9D0B18).

シンプルな「訪問あたりのページビュー数」指標の作成方法を次に示します。

1. 計算指標ビルダーに移動します。
1. 指標に「訪問あたりのページビュー数」などの名前を付けます。
1. ユーザーにわかりやすい指標の用途を「**[!UICONTROL 説明]」に入力します。**
1. Select the right **[!UICONTROL Format]**, in this case Decimal.
1. レポートに表示する小数点以下の桁数を指定します。
1. 指標の両極性を設定します。この指標の場合、上昇傾向は良い（緑）状態であると見なされます。
1. **[!UICONTROL タグ]を追加して指標を管理します。**
1. この指標の場合、最初に「ページビュー数」をキャンバスにドラッグしてから、その下に「訪問回数」をドラッグします（青色の線が表示されるまで待ってからドロップしてください）。
1. 除算演算子を選択します（除算がデフォルトの演算子です）。
1. これで、指標の作成時に、その指標の&#x200B;**[!UICONTROL プレビュー]を右上に表示できます。**
1. 製品の互換性は、指標が「[現在のデータ](https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html)」と互換性があるかどうか、または「処理済みのデータ」とのみ互換性があるかどうかを示します。
1. 「**[!UICONTROL 保存]**」をクリックします。
1. 「**[!UICONTROL 概要]」の数式は、指標の定義を変更すると更新されます。**
1. You are now automatically taken to the [Calculated Metric Manager](../../../../../components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md#concept_BA6815CB06D842D5825766396B691653), which is similar to the Segment Manager. 計算指標マネージャを使用すると、指標の共有、承認、（再）タグ付け、名前変更または削除を行うことができます。

