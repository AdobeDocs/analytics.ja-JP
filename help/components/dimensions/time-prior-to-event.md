---
title: イベント前の時間
description: 指標から訪問の最初のヒットまでの時間。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 78%

---


# イベント前の時間

「イベント前の時間」ディメンションは、訪問の最初のヒットから目的の指標までの経過時間をレポートします。このディメンションは、フォームの送信や購入など、成功イベントに到達するまでの時間を判断するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、技術的にはすべての実装で初期設定の状態で機能しますが、カスタムおよび購入イベントで最も効果的です。サイトにカスタムイベントを実装することをお勧めします。カスタムイベントを実装する場合、このディメンションに追加の実装は必要ありません。

## Dimension項目

Dimension items include time-based buckets ranging from `"Less than 1 minute"` to `"More than 15 hours"`. For example, if it took a visitor 23 minutes from their first hit to a purchase, it would belong under the `"10 to 30 minutes"` dimension item.
