---
title: cookie サポート
description: ブラウザーが cookie をサポートするかどうかを指定します。
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
translation-type: ht
source-git-commit: 4c726cc78e4d6c15db70ab04b0319b0602a51be6
workflow-type: ht
source-wordcount: '187'
ht-degree: 100%

---

# cookie サポート

「Cookie サポート」ディメンションは、ブラウザーが特定のヒットに対して cookie をサポートしているかどうかをレポートします。これは、cookie をサポートするブラウザーを使用する訪問者と cookie を意図的に無効にするブラウザーの割合を判断するのに役立ちます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`k`クエリー文字列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、`s_cc` という名前の cookie を設定しようとし 、その cookie が存在するかどうかを検出します。結果は、クエリー文字列パラメータの値 `Y`（ブラウザーが cookie をサポートし、有効にしている場合）または `N`（ブラウザーが cookie を無効にしている場合）です。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外のデータ収集方式（API 経由など）を使用する場合は、各ヒットに `k` クエリー文字列パラメーターを値 `Y` または `N` で含めてください。

## ディメンション項目

ディメンション項目の値には、`Enabled`、`Disabled`、`Unknown` が含まれます。

* **`Enabled`**：ブラウザーは cookie をサポートし、cookie を有効にしています。
* **`Disabled`**：ブラウザーが cookie をサポートしていないか、訪問者が cookie を無効にしています。
* **`Unknown`**：AppMeasurement は cookie サポートを判断できませんでした。イメージリクエストに `k` クエリー文字列が存在しませんでした。
