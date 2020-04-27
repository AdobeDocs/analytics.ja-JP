---
description: 日付が記入されたセルを選択して、日付範囲を指定することができます。Report Builder では、リクエストでこの特定の日付範囲情報が使用されます。今日の日付を選択すると、リクエストが実行される時刻に基づいて、更新中の未確定データが表示されます。
title: セルからの日付の指定
topic: Report builder
uuid: 0d9bf08d-d39d-4f37-94f1-232da0813245
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# セルからの日付の指定

日付が記入されたセルを選択して、日付範囲を指定することができます。Report Builder では、リクエストでこの特定の日付範囲情報が使用されます。今日の日付を選択すると、リクエストが実行される時刻に基づいて、更新中の未確定データが表示されます。

**セルから日付を設定するには**

1. で、を選 [!UICONTROL Request Wizard: Step 1]択します **[!UICONTROL Dates From Cell]**。
1. Enter cell references in the **[!UICONTROL From]** and **[!UICONTROL To]** fields, or click the selector and select the cells containing the requests with the starting and ending dates.
例えば、日付範囲を「昨日」に設定した Report Builder リクエストを作成し、「today()-1」と同じセルにリクエスト日を出力します。
