---
title: 識別された状態
description: デバイスグラフによる認識を決定するフラグ。
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 9%

---


# 識別された状態

「識別された状態」ディメンションは、 [デバイス間のAnalytics](../cda/overview.md) 仮想レポートスイートに固有です。 レポートの実行時にExperience CloudグラフでデバイスIDが認識されたかどうかを報告します。 このディメンションは、CDAによるデータのステッチ（「圧縮」）の精度を理解するのに役立ちます。

## このディメンションへのデータ入力

仮想レポートスイート用に [クロスデバイス分析](../cda/overview.md) が設定されている限り、このディメンションは初期設定の状態で機能します。

## ディメンション項目

ディメンション項目には、`"Identified"` および `"Unidentified"` が含まれます。

* **`"Identified"`**:デバイスグラフは、ヒットに関連付けられたExperience CloudIDを認識します。
* **`"Unidentified"`**:デバイスグラフがExperience CloudIDを認識しないか、ヒットにExperience CloudIDがない。
