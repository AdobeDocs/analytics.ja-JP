---
title: 特定された状態
description: デバイスグラフによる認識を決定するフラグ。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 89%

---

# 特定された状態

「識別済みの状態」 [ ディメンション ](overview.md) は、[ クロスデバイス分析 ](../cda/overview.md) 仮想レポートスイートに固有です。 レポートの実行時点で、ヒットがシステムによって識別（ステッチ）されているかどうかをレポートします。このディメンションは、CDA によるデータのステッチ（「圧縮」）の精度を理解するのに役立ちます。

## このディメンションへのデータ入力

仮想レポートスイート用に[クロスデバイス分析](../cda/overview.md)が設定されている限り、このディメンションは初期設定のままで機能します。

## ディメンション項目

ディメンション項目には、`"Identified"` および `"Unidentified"` が含まれます。

* **`"Identified"`**：ヒットが個人にマッピングされます。
* **`"Unidentified"`**：ヒットは個人にマッピングされず、どのアトリビューションメソッドでもマッピングできませんでした。
