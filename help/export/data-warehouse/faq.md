---
title: Data Warehouse に関するよくある質問
description: Data Warehouse に関するよくある質問です。
feature: Data Warehouse
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 84%

---

# Data Warehouse に関するよくある質問

Data Warehouse に関するよくある質問です。

## リクエストの作成時に精度ドロップダウンリストを使用すると、日付の形式はどのようになりますか？

Data Warehouse リクエストで精度を適用する場合、「日付」列がレポートに追加されます。 選択した精度に応じて、日付の形式が変わります。

| 精度 | 形式 | 例 |
| --- | --- | --- |
| 1 時間ごと | `mmmm d, yyyy` 時間 `H` | 20XX 年 1 月 1 日、 0 時 |
| 毎日 | `mmmm d, yyyy` | 20XX 年 1 月 1 日 |
| 毎週 | 週 `w, yyyy` | 20XX 年 第 1 週 |
| 毎月 | `mmmm yyyy` | 20XX 年 1 月 |
| 毎四半期 | `q` 四半期 `yyyy` | 20XX 年 第 1 四半期 |
| 毎年 | `yyyy` | 20XX |

## Data Warehouse におけるディメンションとしてのセグメントの動作

Data Warehouse でディメンションとしてセグメントを使用すると、レポートから`"0"` または `"1"` を含む列が返されます。

* **`"0"`**：ディメンション項目がセグメントの条件を満たしていません。
* **`"1"`**：ディメンション項目がセグメントの条件を満たしています。
