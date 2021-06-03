---
description: 時間分割は、収集したヒットのタイムスタンプを取得し、「時間帯」や「曜日」など、よりわかりやすいディメンションに分類します。
title: 時間分割ディメンション
uuid: c9fa7921-aa57-483c-b2f9-da55013ada17
feature: Workspace の基本
role: Business Practitioner, Administrator
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 96%

---

# 時間分割ディメンション

時間分割は、収集したヒットのタイムスタンプを取得し、「時間帯」や「曜日」など、よりわかりやすいディメンションに分類します。

時間分割ディメンションは、レポートスイートまたは仮想レポートスイートのタイムゾーンに基づいています。これらのディメンションは Analysis Workspace で使用でき、以下の問いへの回答を得られます。

* 長い期間を対象にすると、訪問者がサイトまたはアプリに最もよくアクセスする時間帯はどれか。
* サイトまたはアプリでコンバージョンが増加する曜日または時間帯はあるか。
* 平日の売上と比較すると、週末の売上はどうか。
* 特定のマーケティングキャンペーンでコンバージョンが高いのは午前中か、それとも午後か。

>[!NOTE]
>
>時間分割ディメンションは、Analysis Workspace でのみ使用できます。時間分割ディメンションを別の Analytics ソリューションで使用するには、[getTimeParting プラグイン](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/gettimeparting.html)を実装します。

Analysis Workspace の時間分割ディメンションに含まれるものを以下に示します。

| ディメンション | 値の例 |
|--- |--- |
| 時刻 | 0～23 |
| 午前／午後 | 午前、午後 |
| 曜日 | 月曜日、火曜日、水曜日、木曜日、金曜日、土曜日、日曜日 |
| 平日 / 週末 | 週末、平日 |
| 日付 | 1～31 |
| 月 | 1 月～12 月 |
| 年間通算日 | 1～366 |
| 四半期 | 第 1 四半期、第 2 四半期、第 3 四半期、第 4 四半期 |
