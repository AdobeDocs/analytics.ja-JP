---
title: Data WarehouseFAQ
description: Data Warehouseに関するよくある質問です。
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---


# Data WarehouseFAQ

Data Warehouseに関するよくある質問です。

## リクエストの作成時に精度のドロップダウンを使用すると、日付の形式を指定できますか。

Data Warehouseリクエストで精度を適用する場合、「日付」列がレポートに追加されます。 選択した精度に応じて、日付の形式が変わります。

| 精度 | 形式 | 例 |
| --- | --- | --- |
| 1 時間ごと | `mmmm d, yyyy` Hour `H` | 20XX年1月1日、時間0 |
| 毎日 | `mmmm d, yyyy` | 20XX年1月1日 |
| 毎週 | 週 `w, yyyy` | 20XX年1週間 |
| 毎月 | `mmmm yyyy` | 20XX年1月 |
| 毎四半期 | `q` 四半期 `yyyy` | 20XX年第1四半期 |
| 毎年 | `yyyy` | 20XX |

## ディメンションとしてのセグメントのData Warehouseでの動作

セグメントをData Warehouseのディメンションとして使用すると、レポートから次の値を含む列が返され `"0"` ます。また、次の値を含む列が返され `"1"`ます。

* **`"0"`**:ディメンション項目がセグメントの条件を満たしていません。
* **`"1"`**:ディメンション項目がセグメントの条件を満たしている。
