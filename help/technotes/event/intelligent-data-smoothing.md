---
title: インテリジェントデータスムージング
description: インテリジェントデータスムージングが過去のトレンドを分析し、影響を受けた期間内の任意の指標の価値を予測する方法を説明します。
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
TQID: 'https://experienceleague.adobe.com/iqjuEBGaCRcwmWfZo6rC1DXi8y4iyj9gB87tpvXmJdk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 50f9ff18816ad88f231762b8b37c1ab9e1787b6f
workflow-type: tm+mt
source-wordcount: 256
ht-degree: 3%

---

# インテリジェントデータスムージング

まれに、いくつかの要因がデータ品質に影響を与える可能性があります。 ボットトラフィック、実装の変更、サービスの中断はすべて、収集したデータの整合性に影響を与える可能性があります。 また、イベントがデータの完全性にどのような影響を与えたのかを分析するプロセスも複雑になります。

インテリジェントデータスムージングは、[Analytics Labs](/help/analyze/labs.md)のプロトタイプで、過去の傾向を分析して、影響を受ける期間内の任意の指標の値を予測することで、このビューを完成させるのに役立ちます。 プロトタイプでは、高度なマシンラーニングアルゴリズムを使用して、分析対象の期間における指標の期待値をプロットします。

## インテリジェントなデータスムージングの実行

1. Adobe Analytics Labsに移動します。
   ![Labs](assets/labs.png)
1. インテリジェントデータスムージングのプロトタイプを起動します。
   ![&#x200B; プロトタイプを起動](assets/intelligent-ds.png)
1. 分析する必要がある指標をフリーフォームテーブルに追加します。 プロトタイプは毎日の粒度でのみ機能するので、テーブルのディメンションが「日」になっていることを確認します。
   ![指標の追加](assets/add-metric.png)
1. イベントのウィンドウよりも広い日付範囲を選択しますが、イベントが含まれていることを確認してください。
   ![日付範囲](assets/date-range.png)
1. フリーフォームテーブルの指標の歯車アイコンをクリックします。
   ![歯車アイコン &#x200B;](assets/gear-icon.png)
1. [!UICONTROL &#x200B; データ設定]で、[!UICONTROL &#x200B; データスムージング &#x200B;] オプションを選択します。
   ![&#x200B; データのスムージング &#x200B;](assets/column-setting.png)
1. イベントに対応する日付/日付範囲を選択し、[!UICONTROL 適用]をクリックします。
データスムージングのデータ範囲が、パネルで選択した日付範囲のサブセットであることを確認します。 テーブルとグラフの指標は、予測値に置き換えられます。
   ![予測値](assets/predictive-values.png)
