---
title: 訪問数
description: 訪問者の n 番目の訪問。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 59%

---


# 訪問数

訪問者が現在訪問している「訪問回数」ディメンションレポート。新しい訪問の開始時に、このディメンション項目は1ずつ増えます。 このディメンションは、サイトに戻ったときの関与訪問者の行動を把握する場合に役立ちます。これは訪問ベースのディメンションです。つまり、訪問全体で同じ値が含まれ、変更することはできません。プロジェクトの日付範囲に関係なく、訪問者の有効期間に適用されます。

## このディメンションへのデータ入力

このディメンションは、すべての実装で初期設定の状態で動作します。レポートスイートにデータが含まれる場合、このディメンションは機能します。

## Dimension項目

Dimension items include the string `"Visit number"` followed by the numeric representation of the visit the visitor is currently on. For example, if the visitor has never been to your site before, their first visit belongs to the dimension item `"Visit number 1"`. If this is the visitor&#39;s 13th visit to your site, they belong to the dimension item `"Visit number 13"`.
