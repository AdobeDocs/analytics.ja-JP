---
title: Java 有効
description: Java がブラウザーで有効になっているかどうかを特定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---


# Java 有効

「Java 有効」ディメンションは、その時のブラウザーで Java が有効になっているかどうかを指定します。Java ベースの機能をサイトに導入し、既に Java が有効になっている訪問者の数を知りたい場合に便利です。Java を無効にしているユーザーには、Java を有効にする方法に関する代替情報や指示を提供できます。

## このディメンションへのデータ入力

このディメンションは、イメージリクエストの[`v`クエリ列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、Java がブラウザーで有効になっているかどうかを検出することで、このデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外のデータ収集方法（API 経由など）を使用する場合は、「Y」または「N」を含む `v` クエリー文字列パラメーターを必ず含めてこのディメンションを使用してください。

## ディメンション項目

ディメンション項目には、「有効」、「無効」、「不明」があります。

* **有効**：Java がブラウザーで有効になっている。`v` クエリー文字列には値「Y」が含まれていました。 
* **無効**：Java がブラウザーで無効になっているか、無効になっていなくても Java がサポートされていません。`v` クエリー文字列には値「N」が含まれていました。 
* **不明**：AppMeasurement は Java サポートを特定できませんでした。イメージリクエストに `v` クエリー文字列が存在しませんでした。
