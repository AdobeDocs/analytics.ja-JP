---
description: Analysis Workspace のディメンションおよびディメンション項目を分類します。
keywords: Analysis Workspace
title: ディメンションの分類
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
feature: Workspace の基本
role: Business Practitioner, Administrator
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 96%

---

# ディメンションの分類

Analysis Workspace のディメンションおよびディメンション項目を分類します。

特定のニーズに合わせて様々な方法でデータを分類し、関連する指標、ディメンション、セグメント、タイムライン、その他の分析分類値を使用するクエリを作成します。

1. データテーブルを使用して[プロジェクトを作成](/help/analyze/analysis-workspace/home.md)します。
1. データテーブルで行項目を右クリックし、**[!UICONTROL 分類]**／*`<item>`*&#x200B;を選択します。

   ![手順の結果](assets/fa_data_table_actions.png)

   選択した期間で、ディメンション項目またはオーディエンスセグメントで指標を分類できます。より詳細なレベルまで、さらに詳しく調べることもできます。

   >[!NOTE]
   >
   >テーブルに表示する分類の数は、200 までに制限されています。この制限は、分類をエクスポートする場合は増加します。

[Analysis Workspace のプロジェクトへのディメンションと指標の追加](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/metrics/adding-dimensions-and-metrics-to-your-project-in-analysis-workspace.html)（11:39）

[フリーフォームテーブルでのディメンションの操作](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/working-with-dimensions-in-a-freeform-table.html)（15:35）

## 分類へのアトリビューションモデルの適用

テーブル内の分類には、任意のアトリビューションモデルを適用することもできます。このアトリビューションモデルは、親列と同じ場合と異なる場合があります。例えば、マーケティングチャネルディメンションで線形の注文件数を分析するものの、チャネル内の特定のトラッキングコードには U 字形の注文件数を適用するといったことができます。分類に適用されるアトリビューションモデルを編集するには、その分類モデルの上にマウスポインターを置いて「**[!UICONTROL 編集]**」をクリックするだけです。

![分類の設定](assets/breakdown_settings.png)
