---
description: 時間分割ディメンションが収集したイベントのタイムスタンプを取得し、これらのイベントをより意味のあるディメンション（時間帯や曜日など）に分類する方法について説明します。
title: 時間分割ディメンション
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 20%

---

# 時間分割ディメンション

時間分割は、収集したヒットのタイムスタンプを取得し、**時間帯** や **曜日** など、よりわかりやすいディメンションに分類します。


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[Time-parting dimensions](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/time-parting-dimensions-in-analysis-workspace){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


時間分割ディメンションは、レポートスイートまたは仮想レポートスイートのタイムゾーンに基づいています。 これらのディメンションは、Analysis Workspaceで使用でき、次の質問に答えるのに役立ちます。

* 大きな日付範囲において、訪問者がサイトやアプリにアクセスする最も人気のある時間帯を教えてください。
* サイトやアプリでのコンバージョンが高い曜日や時間はありますか？
* 週末の売り上げと平日の売り上げはどのように比較されますか。
* 特定のマーケティングキャンペーンは、午前中と午後のどちらでより高いコンバージョンを生成しますか？

>[!NOTE]
>
>時間分割ディメンションは、Analysis Workspace でのみ使用できます。他の Analytics ソリューションで時間分割ディメンションを使用するには、[getTimeParting プラグイン ](/help/implement/vars/plugins/gettimeparting.md) を実装します。

Analysis Workspaceの時間分割ディメンションには、次のものが含まれます。

| ディメンション | 値の例 |
| --- | --- |
| 時刻 | 0 ～ 23 |
| 午前／午後 | 午前、午後 |
| 曜日 | 月曜日、火曜日、水曜日、木曜日、金曜日、土曜日、日曜日 |
| 週末/平日 | 週末、平日 |
| 日付 | 1 ～ 31 |
| 月 | 1 月 ～ 12 月 |
| 年間通算日 | 1 ～ 366 |
| 四半期 | 第 1 四半期、第 2 四半期、第 3 四半期、第 4 四半期 |
