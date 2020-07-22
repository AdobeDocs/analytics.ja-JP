---
title: cookieのサポート
description: ブラウザーがcookieをサポートするかどうかを指定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---


# cookie サポート

「cookieのサポート」ディメンションは、ブラウザーが特定のヒットに対してcookieをサポートしているかどうかをレポートします。 cookieをサポートするブラウザーを使用する訪問者と、cookieを意図的に無効にするブラウザーの割合を判断すると役立ちます。

## このディメンションにデータを入力する

このディメンションは、イメージリクエストの [`k` クエリ列](/help/implement/validate/query-parameters.md) からデータを収集します。 AppMeasurementは、という名前のcookieを設定しようとし `s_cc`、そのcookieが存在するかどうかを検出します。 結果は、クエリ文字列パラメータの値 `Y` （ブラウザーがcookieをサポートし、有効にしている場合）または `N` （ブラウザーがcookieを無効にしている場合）です。 (Adobe Experience Platformの起動を介したなど)AppMeasurementを使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement以外のデータ収集方法（API経由など）を使用する場合は、各ヒットに `k` クエリ文字列パラメーターを値 `Y` またはと共に含めてください `N`。

## ディメンション項目

ディメンション項目には、 `Enabled`、、 `Disabled`およびが含まれ `Unknown`ます。

* **`Enabled`**: ブラウザーはcookieをサポートし、cookieを有効にしています。
* **`Disabled`**: ブラウザーがcookieをサポートしていないか、訪問者がcookieを無効にしています。
* **`Unknown`**: AppMeasurementはcookieのサポートを判断できませんでした。 イメージ要求に `k` クエリ文字列が存在しませんでした。
