---
description: シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。
title: シンプルな「訪問あたりのページビュー数」指標の作成
uuid: 0730e51c-1f8f-473b-8825-d72911f2944c
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# シンプルな「訪問あたりのページビュー数」指標の作成

シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。

UI コンポーネントについて詳しくは、「[指標の作成](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)」を参照してください。

シンプルな「訪問あたりのページビュー数」指標の作成方法を次に示します。

1. 計算指標ビルダーに移動します。
1. 指標に「訪問あたりのページビュー数」などの名前を付けます。
1. Give it a user-friendly **[!UICONTROL Description]** to show what it&#39;s used for.
1. Select the right **[!UICONTROL Format]**, in this case Decimal.
1. レポートに表示する小数点以下の桁数を指定します。
1. 指標の両極性を設定します。この指標の場合、上昇傾向は良い（緑）状態であると見なされます。
1. Add a **[!UICONTROL Tag]** to organize your metrics.
1. この指標の場合、最初に「ページビュー数」をキャンバスにドラッグしてから、その下に「訪問回数」をドラッグします（青色の線が表示されるまで待ってからドロップしてください）。
1. 除算演算子を選択します（除算がデフォルトの演算子です）。
1. You can now see a **[!UICONTROL Preview]** of that metric as you are building it, at the top right.
1. 製品の互換性は、指標が「[現在のデータ](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html)」と互換性があるかどうか、または「処理済みのデータ」とのみ互換性があるかどうかを示します。
1. クリック **[!UICONTROL Save]**.
1. Notice that the **[!UICONTROL Summary]** formula updates anytime you make a change to the metric definition.
1. セグメントマネージャに似た[計算指標マネージャ](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)へと自動的に移動します。計算指標マネージャを使用すると、指標の共有、承認、（再）タグ付け、名前変更または削除を行うことができます。

