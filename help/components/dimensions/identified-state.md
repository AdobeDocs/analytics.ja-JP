---
title: 特定された状態
description: デバイスグラフによる認識を決定するフラグ。
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '120'
ht-degree: 100%

---

# 特定された状態

「識別された状態」ディメンションは、[クロスデバイス分析](../cda/overview.md)仮想レポートスイートに固有です。 レポートの実行時にデバイスグラフで Experience Cloud ID が認識されたかどうかを報告します。 このディメンションは、CDA によるデータのステッチ（「圧縮」）の精度を理解するのに役立ちます。

## このディメンションへのデータ入力

仮想レポートスイート用に[クロスデバイス分析](../cda/overview.md)が設定されている限り、このディメンションは初期設定のままで機能します。

## ディメンション項目

ディメンション項目には、`"Identified"` および `"Unidentified"` が含まれます。

* **`"Identified"`**：デバイスグラフは、ヒットに関連付けられた Experience Cloud ID を認識します。
* **`"Unidentified"`**：デバイスグラフが Experience Cloud ID を認識しないか、ヒットに Experience Cloud ID がありません。
