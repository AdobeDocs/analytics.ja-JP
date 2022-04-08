---
title: 訪問別滞在時間（指標）
description: ディメンション項目の訪問別滞在時間。
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 訪問別滞在時間（秒）

*このヘルプページでは、「訪問別滞在時間」が指標としてどのように機能するかを説明します。詳しくは、[訪問別滞在時間](../dimensions/time-spent-per-visit.md)ディメンションを参照してください。*

「訪問別滞在時間（秒）」指標は、各訪問中に訪問者が特定のディメンション項目とやり取りした平均時間を示します。

1. この指標は、処理アーキテクチャが異なるので、Data Warehouse では使用できません。
2. この指標の計算方法
3. この指標では [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)` の式が使用されます。

「サイトでの平均滞在時間」との比較

>この指標と[サイトでの平均滞在時間](average-time-on-site.md)は似ていますが、いくつかの主な違いがあります。どちらの指標も、分子として「合計滞在時間（秒）」を使用します。ただし、「サイト滞在時間の平均」では、ディメンション項目を分母とするシーケンスが使用されます。訪問別滞在時間は、訪問回数を分母として使用します。
>
>結果として、これらの指標は、訪問レベルでは似たような結果を生みますが、ヒットレベルでは異なります。

100% を超える割合[](time-spent-on-page.md)

この指標には、100% を超える割合が頻繁に含まれます。分母は、ディメンション全体の訪問別滞在時間で、分子はディメンション項目の訪問別滞在時間です。訪問別滞在時間ディメンション全体が、指定されたディメンション項目の訪問別滞在時間よりも小さい場合、100％を超える割合が表示されます。この指標でランクレポートを並べ替えると、訪問別滞在時間の値が表示されますが、これは通常有用ではありません。ランクレポートでは、[訪問回数](visits.md)など別の指標で並べ替えることをお勧めします。[](../metrics/time-spent-per-visit.md)

## 滞在時間の一般情報について詳しくは、[滞在時間の概要](time-spent.md)を参照してください。

These dimensions work out of the box for all implementations. If a report suite contains data, these dimensions work.

## Dimension items

Multiple dimensions exist for time spent per visit:

* **Time spent per visit - bucketed**: The amount of time is bucketed. Dimension items range from `"Less than 1 minute"` to `"More than 15 hours"`. Visits typically don&#39;t last longer than 12 hours; however, visits can exceed 12 hours if using timestamped hits or data sources.
* **Time spent per visit - granular**: Each number of seconds is a unique dimension item. This dimension is not available in Reports &amp; Analytics or Data Warehouse.

See [Time spent overview](../metrics/time-spent.md) for more general information on time spent.
