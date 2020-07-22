---
title: Java 有効
description: ブラウザーでJavaが有効かどうかを指定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 1%

---


# Java 有効

「Javaが有効」ディメンションは、その時のブラウザーでJavaが有効になっているかどうかを指定します。 Javaベースの機能をサイトに導入し、既にJavaが有効になっている訪問者の数を知りたい場合に便利です。 Javaを無効にしているユーザーには、Javaを有効にする方法に関する代替情報や指示を提供できます。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`v` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、Javaがブラウザーで有効になっているかどうかを検出することで、このデータを収集します。 (Adobe Experience Platform起動を介したなどの)AppMeasurementライブラリを使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement以外（API経由など）でデータ収集方法を使用する場合、このディメンションを使用する場合は、「Y」または「N」を含む `v` クエリ文字列パラメーターを必ず含めてください。

## ディメンション項目

ディメンション項目には、「有効」、「無効」、「不明」があります。

* **有効**: Javaがブラウザーで有効になっている。 クエリ文字列には値「Y」が含まれていました。 `v`
* **無効**: Javaがブラウザーで無効になっているか、それ以外の場合はJavaがサポートされていません。 クエリ文字列には値「N」が含まれていました。 `v`
* **不明**: AppMeasurementはJavaサポートを特定できませんでした。 イメージ要求に `v` クエリ文字列が存在しませんでした。
