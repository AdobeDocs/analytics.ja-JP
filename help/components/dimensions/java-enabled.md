---
title: Java 有効
description: Java がブラウザーで有効になっているかどうかを特定します。
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
TQID: https://experienceleague.adobe.com/EjiqmqpByH-q9AL-934s5HXAv78JTXpEJZ1Bwk-y5MI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 93%

---

# Java 有効

「Javaが有効になりました」 [ ディメンション ](overview.md)は、当時のブラウザーでJavaが有効になっているかどうかを判断します。 Java ベースの機能をサイトに導入し、既に Java が有効になっている訪問者の数を知りたい場合に便利です。 Java を無効にしているユーザーには、Java を有効にする方法に関する代替情報や指示を提供できます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`v`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。 AppMeasurement は、Java がブラウザーで有効になっているかどうかを検出することで、このデータを収集します。 AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement 以外のデータ収集方法（API 経由など）を使用する場合は、「Y」または「N」を含む `v` クエリ文字列パラメーターを必ず含めてこのディメンションを使用してください。

## ディメンション項目

ディメンション項目には、「有効」、「無効」、「不明」があります。

* **有効**：Java がブラウザーで有効になっている。 `v` クエリ文字列には値「Y」が含まれていました。
* **無効**：Java がブラウザーで無効になっているか、無効になっていなくても Java がサポートされていません。 `v` クエリ文字列には値「N」が含まれていました。
* **不明**：AppMeasurement は Java サポートを特定できませんでした。 イメージリクエストに `v` クエリ文字列が存在しませんでした。
