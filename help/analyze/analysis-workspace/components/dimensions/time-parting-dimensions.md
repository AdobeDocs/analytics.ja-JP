---
description: 時間分割ディメンションが、収集したイベントのタイムスタンプをどのように取得し、これらのイベントをより有意義なディメンション（時間帯や曜日など）に分割するかをご紹介します。
title: 時間分割ディメンション
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
TQID: https://experienceleague.adobe.com/bQVBmv3KhaDZtmUXSOY3UsustpCZKAwJ8rH9Qv49Rfw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 19%

---

# 時間分割ディメンション

タイムパーティングでは、収集したヒットのタイムスタンプを取得し、**時間**&#x200B;や&#x200B;**曜日**&#x200B;など、より意味のあるディメンションに分割します。


>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [時間分割ディメンション &#x200B;](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/time-parting-dimensions-in-analysis-workspace){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


時間分割ディメンションは、レポートスイートまたは仮想レポートスイートのタイムゾーンに基づいています。 これらのディメンションはAnalysis Workspaceで利用でき、次の質問に答えるのに役立ちます。

* 幅広い日付範囲で、訪問者がサイトやアプリにアクセスする最も人気のある時間帯は何ですか？
* サイトやアプリで、コンバージョン率が高い曜日や時間帯はありますか？
* ウィークエンドの売上とウィークエンドの売上の比較はどうなりますか？
* 「特定のマーケティング施策は、午前中にコンバージョン率を向上させますか？」

>[!NOTE]
>
>時間分割ディメンションは、Analysis Workspace でのみ使用できます。 他のAnalytics ソリューションで時間分割ディメンションを使用するには、[getTimeParting プラグイン &#x200B;](/help/implement/vars/plugins/gettimeparting.md)を実装できます。

Analysis Workspaceの時間分割ディメンションには、次のものがあります。

| ディメンション | 値の例 |
| --- | --- |
| 時刻 | 0 ～ 23 |
| 午前／午後 | AM、PM |
| 曜日 | 月曜日、火曜日、水曜日、木曜日、金曜日、土曜日、日曜日 |
| 週末/平日 | 週末、平日 |
| 日付 | 1 ～ 31 |
| 月 | 1 月 ～ 12 月 |
| 年間通算日 | 1 ～ 366 |
| 四半期 | 第 1 四半期、第 2 四半期、第 3 四半期、第 4 四半期 |
