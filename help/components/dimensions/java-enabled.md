---
title: Java 有効
description: Java がブラウザーで有効になっているかどうかを特定します。
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 93%

---

# Java 有効

「Java 対応」 [ ディメンション ](overview.md) は、その時点でブラウザーが Java を有効にしているかどうかを判断します。 Java ベースの機能をサイトに導入し、既に Java が有効になっている訪問者の数を知りたい場合に便利です。Java を無効にしているユーザーには、Java を有効にする方法に関する代替情報や指示を提供できます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`v`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、Java がブラウザーで有効になっているかどうかを検出することで、このデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外のデータ収集方法（API 経由など）を使用する場合は、「Y」または「N」を含む `v` クエリ文字列パラメーターを必ず含めてこのディメンションを使用してください。

## ディメンション項目

ディメンション項目には、「有効」、「無効」、「不明」があります。

* **有効**：Java がブラウザーで有効になっている。`v` クエリ文字列には値「Y」が含まれていました。
* **無効**：Java がブラウザーで無効になっているか、無効になっていなくても Java がサポートされていません。`v` クエリ文字列には値「N」が含まれていました。
* **不明**：AppMeasurement は Java サポートを特定できませんでした。イメージリクエストに `v` クエリ文字列が存在しませんでした。
