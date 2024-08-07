---
title: 時刻
description: 時刻を数値で表します。日付は関係ありません。
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 95%

---

# 時刻

「時刻」 [ ディメンション ](overview.md) は、任意の日の数値時間をディメンション項目としてレポートします。 例えば、1 月 1 日から 1 月 7 日にまたがるレポートがある場合、各日の最初の時刻は、同じディメンション項目にグループ化されます。このレポートは、時刻別にレポートを分類するが、ディメンション項目として静的な日数を必要としない場合に役立ちます。このディメンションは、選択した日付範囲でロールするので、予定レポートのディメンションとして特に役立ちます。

このディメンションは、訪問者のローカルタイムゾーンではなく、レポートスイートのタイムゾーンに基づいています。例えば、レポートスイートが山岳部時間で、カリフォルニア州の訪問者が太平洋時間の午前 10 時にサイトを訪問した場合、`11:00 AM` ディメンション項目下にヒットグループが表示されます。ローカル訪問者の時間を記録するディメンションが必要な場合、 [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) プラグインの使用をお勧めします。

## このディメンションへのデータ入力

このディメンションは、すべての実装において初期設定の状態で動作します。レポートスイートにデータが含まれていれば、このディメンションは機能します。

## ディメンション項目

ディメンション項目には `12:00 AM` ～ `11:00 PM` が含まれます。これは、ヒットが発生した日の時間（切り捨て）を表します。例えば、ヒットが午後 3 時 58 分に生成された場合、そのヒットは、`3:00 PM` のディメンション項目の下にグループ化されます。

## 夏時間

夏時間は、時計を春に 1 時間戻し、秋に 1 時間進める習慣です。レポートスイートのタイムゾーンで DST が使用されている場合、その時間に応じてデータが調整されます。

* **夏時間の開始**：3 月には、夏時間が開始するときに通常、レポートのデータに 1 時間の差があります。この時間は存在しなかったので、データ収集の一部にはなりません。少量のデータがこの時間に表示される可能性があります。アドビのデータ収集サーバーでは、DST による調整を考慮するのに、数秒（最大 1 分）かかります。
* **夏時間の終了**：11 月には、夏時間が終了するときに通常、レポートに重複時間が表示されます。時間が 2 回発生するので、両方の時間がレポートで集計されます。
