---
description: シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。
title: シンプルな「訪問あたりのページビュー数」指標の作成
feature: Calculated Metrics
exl-id: 2d1c4677-b07c-4eca-97b7-e5e4594daee1
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '249'
ht-degree: 100%

---

# シンプルな「訪問あたりのページビュー数」指標の作成

シンプルな「訪問あたりのページビュー数」指標の作成方法を示します。

UI コンポーネントについて詳しくは、「[指標の作成](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)」を参照してください。

シンプルな「訪問あたりのページビュー数」指標の作成方法を次に示します。

1. 計算指標ビルダーに移動します。
1. 指標に「訪問あたりのページビュー数」などの名前を付けます。
1. ユーザーにわかりやすい指標の用途を「**[!UICONTROL 説明]**」に入力します。
1. 適切な「**[!UICONTROL 形式]**」を選択します。ここでは「小数」です。
1. レポートに表示する小数点以下の桁数を指定します。
1. 指標の両極性を設定します。この指標の場合、上昇傾向は良い（緑）状態であると見なされます。
1. **[!UICONTROL タグ]**&#x200B;を追加して指標を管理します。
1. この指標の場合、最初に「ページビュー数」をキャンバスにドラッグしてから、その下に「訪問回数」をドラッグします（青色の線が表示されるまで待ってからドロップしてください）。
1. 除算演算子を選択します（除算がデフォルトの演算子です）。
1. これで、指標の作成時に、その指標の&#x200B;**[!UICONTROL プレビュー]**&#x200B;を右上に表示できます。
1. 製品の互換性は、指標が「[現在のデータ](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=ja)」と互換性があるかどうか、または「処理済みのデータ」とのみ互換性があるかどうかを示します。
1. 「**[!UICONTROL 保存]**」をクリックします。
1. 「**[!UICONTROL 概要]**」の数式は、指標の定義を変更すると更新されます。
1. セグメントマネージャに似た[計算指標マネージャ](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-manager.md)へと自動的に移動します。計算指標マネージャを使用すると、指標の共有、承認、（再）タグ付け、名前変更または削除を行うことができます。
