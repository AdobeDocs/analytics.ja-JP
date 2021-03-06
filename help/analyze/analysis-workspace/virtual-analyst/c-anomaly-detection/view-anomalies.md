---
description: 異常値をテーブルまたは線グラフで表示できます。
title: Analysis Workspace での異常値の表示
feature: Anomaly Detection
role: User, Admin
exl-id: 32edc7f4-c9b9-472a-b328-246ea5b54d07
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: ht
source-wordcount: '247'
ht-degree: 100%

---

# Analysis Workspace での異常値の表示

異常値はテーブルまたは折れ線グラフで表示できます。

## テーブルの異常値の表示 {#section_869A87B92B574A38B017A980ED8A29C5}

時系列のフリーフォームテーブルで、データの異常値が検出されると、各行に自動的にダークグレーの感嘆符のフラグが設定されるようになりました。

![](assets/anomaly_detected.png)

各行のグレーの縦線は、期待値を示します。感嘆符の上にマウスポインターを置くと、異常値が期待値から離れている程度が示されます（+ または - %）。

## 折れ線グラフの異常値の表示 {#section_7C1192AFDB4345A8A2CCFB3AE0C47D82}

折れ線グラフには、薄緑色の信頼帯が異常値（白い点）と共に表示されます。

白い点をクリックすると緑色に変わり、以下が表示されます。

* 異常値が発生した日付
* 異常値の生の値
* 期待値を上回るまたは下回る割合の値。これは緑の実線で表されます。
* [貢献度分析](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md)を開始するための分析リンク。

![](assets/anomaly_linechart.png)

折れ線グラフに複数の指標がある場合、異常値のみが表示され、その指標の信頼帯を表示するには、各異常値の上にマウスポインターを置く必要があります。

異常値検出の信頼区間では、ビジュアライゼーションの Y 軸を自動的に調整しないので、わかりやすくなります。

信頼区間でチャートを調整できるオプションがあります。設定（歯車）アイコンをクリックして、「**[!UICONTROL 異常値検出で Y 軸のスケールの設定を可能にする]**」をオンにします。

![](assets/scale-y-axis.png)
