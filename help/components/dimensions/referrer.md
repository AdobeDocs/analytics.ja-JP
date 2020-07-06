---
title: リファラー
description: 訪問者がクリックスルーしてサイトにアクセスする前にいたURL。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---


# リファラー

「転送者」ディメンションは、クリックスルーしてサイトに到達したときに訪問者が閲覧したURLをレポートします。 このディメンションは、どの特定のURLがサイトへのトラフィックを最も多く引き起こしているかを把握するのに役立ちます。 ディメンション値を表示するには、外部URLにリンクが存在し、訪問者がリンクをクリックする必要があります。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの [内部URLフィルター](/help/admin/admin/internal-url-filter-admin.md) を設定する必要があります。 内部URLフィルターを設定しないと、内部URLが含まれるか、外部URLが表示されない可能性があります。

## このディメンションにデータを入力する

このディメンションには、Analyticsインターフェイスでの設定とイメージリクエストでのデータが必要です。

* 実装内で、このディメンションはイメージリクエストの [`r` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、ブラウザーのJavaScript変数を使用してこのデータ `document.referrer` を収集します。 (Adobe Experience Platform起動を介したなどの)AppMeasurementライブラリを使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement以外の（API経由などの）データ収集方法を使用する場合は、クエリリクエストに `r` 文字列パラメーターを必ず含めてください。
* Analyticsのインターフェイス内で、レポートスイートの [内部URLフィルターを設定する必要があります](/help/admin/admin/internal-url-filter-admin.md)。 内部URLフィルターを設定しないと、内部URLが含まれるか、外部URLが表示されない可能性があります。

## 分析コード値

ディメンション値には、訪問者がサイトにクリックスルーするURLが含まれます。 ヒットに転送者データがない場合は、ディメンション値でグループ化され `"Typed/Bookmarked"`ます。 このディメンション値は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、転送者値がなかったことを意味します。
