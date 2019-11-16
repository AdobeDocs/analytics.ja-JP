---
description: 特定期間内の昨年の日別サーバーコール数平均に加え、今年のサーバーコールの予想増加量を取得できます。その後、この増倍率に基づいて、トラフィックスパイクをスケジュールできます。
solution: Analytics
title: 過去のサーバーコールの推定とトラフィックスパイクのスケジュール
uuid: 38deb1df-afb0-437d-b541-69295f0dc8dc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 過去のサーバーコールの推定とトラフィックスパイクのスケジュール

特定期間内の昨年の日別サーバーコール数平均に加え、今年のサーバーコールの予想増加量を取得できます。その後、この増倍率に基づいて、トラフィックスパイクをスケジュールできます。

1. Log in to Analytics as an Admin and go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Traffic Management]**.

1. 「**[!UICONTROL 展開]**」をクリックしてレポートスイートのリストを展開し、「**レポートスイートを選択[!UICONTROL 」をクリックして複数のレポートスイートを選択します。]**

1. Click **[!UICONTROL Schedule Spikes]**.
1. Under **[!UICONTROL Past Server Calls]**, select a start and end date for the selected report suites.

   「ピーク日」の値には、「ピーク日のサーバーコール」と「1 日当たりのサーバーコール平均」が生成されます。

1. Input a value for the multiplication factor and click **[!UICONTROL Click to multiply and set]**.

   各レポートスイートの各列の値が乗算されます。

1. Under **[!UICONTROL Set Spike Parameters]**, submit the spike parameters for the selected report suites.

   選択したレポートスイートそれぞれにスパイクがスケジュールされます。

![](assets/past_server_calls.png)

