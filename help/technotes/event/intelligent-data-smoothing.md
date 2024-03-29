---
title: インテリジェントデータスムージング
description: インテリジェントデータスムージングでは、過去のトレンドを分析して、影響を受ける期間内の指標の値を予測する方法を説明します。
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
source-git-commit: e0a4caec9bc58a0846cd46871aad3bed99d218a3
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 3%

---

# インテリジェントデータスムージング

まれに、一部の要因がデータの品質に影響を与える可能性があります。 ボットトラフィック、実装の変更、またはサービスの中断は、収集されたデータの整合性に影響を与える可能性があります。 また、イベントがデータの完全性に与える影響についての分析も複雑になります。

インテリジェントデータスムージングは、 [Analytics Labs](/help/analyze/labs.md) これは、過去のトレンドを分析して、影響を受ける期間内の指標の値を予測することで、このビューを完了するのに役立ちます。 プロトタイプは高度な機械学習アルゴリズムを適用し、分析対象の期間における指標の期待値をグラフ表示します。

## インテリジェントデータスムージングの実行

1. Adobe Analytics Labs に移動します。
   ![ラボ](assets/labs.png)
1. インテリジェントデータスムージングプロトタイプを起動します。
   ![プロトタイプを起動](assets/intelligent-ds.png)
1. 分析が必要な指標をフリーフォームテーブルに追加します。 プロトタイプは 1 日単位の精度でのみ機能するので、テーブルのディメンションが「日」であることを確認します。
   ![指標を追加](assets/add-metric.png)
1. イベントのウィンドウより広い日付範囲を選択しますが、イベントが含まれていることを確認します。
   ![日付範囲](assets/date-range.png)
1. フリーフォームテーブルで、指標の歯車アイコンをクリックします。
   ![歯車アイコン](assets/gear-icon.png)
1. の下 [!UICONTROL データ設定]を選択し、 [!UICONTROL データのスムージング] オプション。
   ![データのスムージング](assets/column-setting.png)
1. イベントに対応する日付/日付範囲を選択し、 [!UICONTROL 適用].
データスムージングのデータ範囲が、パネルで選択した日付範囲のサブセットであることを確認します。 テーブルとグラフの指標が、予測値に置き換えられます。
   ![予測値](assets/predictive-values.png)
