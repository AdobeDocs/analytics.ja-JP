---
title: cookie サポート
description: ブラウザーが cookie をサポートするかどうかを指定します。
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 92%

---

# cookie サポート

&#39;Cookie サポート&#39; [ ディメンション ](overview.md)は、ブラウザーが特定のヒットに対するCookieをサポートしているかどうかを報告します。 これは、cookie をサポートするブラウザーを使用する訪問者と cookie を意図的に無効にするブラウザーの割合を判断するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`k`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 AppMeasurement は、`s_cc` という名前の cookie を設定しようとし、その cookie が存在するかどうかを検出します。 結果は、クエリ文字列パラメータの値 `Y`（ブラウザーが cookie をサポートし、有効にしている場合）または `N`（ブラウザーが cookie を無効にしている場合）です。 AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement 以外のデータ収集方式（API 経由など）を使用する場合は、各ヒットに `k` クエリ文字列パラメーターを値 `Y` または `N` で含めてください。

## ディメンション項目

ディメンション項目の値には、`Enabled`、`Disabled`、`Unknown` が含まれます。

* **`Enabled`**：ブラウザーは cookie をサポートし、cookie を有効にしています。
* **`Disabled`**：ブラウザーが cookie をサポートしていないか、訪問者が cookie を無効にしています。
* **`Unknown`**：AppMeasurement は cookie サポートを判断できませんでした。 イメージリクエストに `k` クエリ文字列が存在しませんでした。
