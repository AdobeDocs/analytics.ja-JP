---
title: 動的および静的Dimension項目
description: Analysis Workspaceのフリーフォームテーブルで動的ディメンション項目と静的ディメンション項目を使用する方法を説明します。
feature: Freeform Tables
role: User, Admin
exl-id: 4cdc93b5-67ed-46a4-ba9f-a96e640da9d9
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 94%

---

# 動的ディメンション項目と静的ディメンション項目

フリーフォームテーブルでは、行と列に様々なコンポーネント値を含めることができます。 これらの値は、作成する分析に応じて、動的（時間の経過と共に変更）または静的（時間と共に変更しない）にできます。

## 動的ディメンション項目

動的ディメンション項目は時間の経過と共に変化し、フリーフォームテーブルで並べ替えられる指標に依存します。特定の期間のトップ項目を分析する場合は、動的ディメンション項目をお勧めします。

フリーフォームテーブルにディメンションをドロップすると、動的な行が返されます。これらは、指定した指標と期間のディメンションに対応するトップ項目を表します。動的な行は、指定した指標と期間のディメンションに対応する上位の項目を表します。また、ディメンションをフリーフォームテーブルの列にドロップすると、ディメンションを自動的に上位 5 つのディメンション項目に展開します。

例えば、ブラウザータイプディメンションをテーブルにドラッグすると、上位のブラウザータイプディメンション項目（Microsoft、Apple、Google など）が動的にテーブル行に返されます。列にドロップすると、上位 5 つのブラウザータイプディメンション項目が動的に返されます。

動的ディメンション項目には、行フィルターオプション ![フィルター](/help/assets/icons/Filter.svg) と ![閉じる](/help/assets/icons/Close.svg) があり、ロック ![LockClosed](/help/assets/icons/LockClosed.svg) は&#x200B;**ありしません**。<!--do they have the lock icon? -->動的ディメンション項目の横にある ![閉じる](/help/assets/icons/Close.svg) をクリックすると、フィルターが自動的に適用されます。テーブルにフィルターを適用する方法について詳しくは、[テーブルのフィルタリングと並べ替え](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)を参照してください。


![フィルターアイコンをハイライト表示するフリーフォームテーブル。](assets/dynamic-items.png)

## 静的ディメンション項目

静的ディメンション項目は、時間と共に変化しません。これらは、常にフリーフォームテーブルに返される固定コンポーネントです。静的ディメンション項目は、同じ項目（特定のキャンペーンでも週の特定の曜日でも）を常に分析する場合にお勧めします。

特定のコンポーネント値（ディメンション、指標、セグメント、日付範囲）を手動で選択してテーブルにドロップすると、結果は行または列の静的なリストになります。

例えば、Microsoft や Apple などの特定のブラウザータイプ項目にドラッグすると、その 2 つの特定の項目が常にテーブルに取り込まれます。

また、静的ディメンション項目は、選択した行のコンテキストメニューから「**[!UICONTROL 選択した行のみを表示]**」を選択した場合にも作成できます。

静的ディメンション項目には行フィルターオプションは&#x200B;**ありません**。代わりに、各項目に ![LockClosed](/help/assets/icons/LockClosed.svg) と ![閉じる](/help/assets/icons/Close.svg) があります。![閉じる](/help/assets/icons/Close.svg) を選択すると、そのディメンション項目がテーブルから削除されます。

![ブラウザータイプとロックアイコン付きの Microsoft 行を表示するフリーフォームテーブル。メモ：このディメンション項目は静的であり、時間の経過と共に変化しません。](assets/static-items.png)

## 混在ディメンション項目

異なるディメンションのディメンション項目を同じテーブルに追加できます。この場合、行ヘッダーには&#x200B;**[!UICONTROL 混合ディメンション]**&#x200B;と表示されます。これらのディメンション項目は静的です。例えば、ブラウザグループディメンションから特定のディメンション項目を追加し、ブラウザー名ディメンションから他のディメンション項目を追加します。

![混合ディメンション列をハイライト表示するフリーフォームテーブル。](assets/mixed-dimensions.png)

## フリーフォームの合計行数

フリーフォーム合計行での動的な行と静的な行の動作は異なります。デフォルトでは:：

* 動的な行はサーバーサイドで合計され、セッションやユーザーなどの指標が重複排除されます。
* 静的な行は、クライアントサイドで合計され、重複を取り除き&#x200B;**ません**。サーバーサイドの合計行を計算するには、「行」設定を「**総合計を表示**」に変更します。[詳細情報](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md)


>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [静的行の並べ替え](https://experienceleague.adobe.com/ja/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/reordering-static-rows-in-analysis-workspace){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


