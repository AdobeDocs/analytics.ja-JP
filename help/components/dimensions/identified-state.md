---
title: 特定された状態
description: デバイスグラフによる認識を決定するフラグ。
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '111'
ht-degree: 100%

---

# 特定された状態

「識別された状態」ディメンションは、[クロスデバイス分析](../cda/overview.md)仮想レポートスイートに固有です。 レポートの実行時点で、ヒットがシステムによって識別（ステッチ）されているかどうかをレポートします。このディメンションは、CDA によるデータのステッチ（「圧縮」）の精度を理解するのに役立ちます。

## このディメンションへのデータ入力

仮想レポートスイート用に[クロスデバイス分析](../cda/overview.md)が設定されている限り、このディメンションは初期設定のままで機能します。

## ディメンション項目

ディメンション項目には、`"Identified"` および `"Unidentified"` が含まれます。

* **`"Identified"`**：ヒットが個人にマッピングされます。
* **`"Unidentified"`**：ヒットは個人にマッピングされず、どのアトリビューションメソッドでもマッピングできませんでした。
