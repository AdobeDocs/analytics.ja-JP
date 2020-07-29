---
title: リファラー
description: 訪問者がクリックスルーしてサイトにアクセスする前にいたURL。
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---


# リファラー

「転送者」ディメンションは、クリックスルーしてサイトに到達したときに訪問者が閲覧したURLをレポートします。 このディメンションは、どの特定のURLがサイトへのトラフィックを最も多く引き起こしているかを把握するのに役立ちます。 ディメンション項目を表示するには、外部URLにリンクが存在し、訪問者がリンクをクリックする必要があります。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの [内部URLフィルター](/help/admin/admin/internal-url-filter-admin.md) を設定する必要があります。 内部URLフィルターを設定しないと、内部URLが含まれるか、外部URLが表示されない可能性があります。

同じレポートに、Analysis WorkspaceとData warehouseで異なる結果が表示される場合があります。 Analysis Workspaceは、内部URLフィルターに一致する値を除き、個々のページの転送者を報告します。 Data warehouseは、訪問の最初の転送者のみを報告し、内部URLフィルターを無視します。

## このディメンションにデータを入力する

このディメンションには、Analyticsインターフェイスでの設定とイメージリクエストでのデータが必要です。

* 実装内で、このディメンションはイメージリクエストの [`r` クエリ列](/help/implement/validate/query-parameters.md) からデータを取得します。 AppMeasurementは、ブラウザーのJavaScript変数を使用してこのデータ `document.referrer` を収集します。 AppMeasurementライブラリ(Adobe Experience Platform Launch経由など)を使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement以外の（API経由などの）データ収集方法を使用する場合は、クエリリクエストに `r` 文字列パラメーターを必ず含めてください。
* Analyticsのインターフェイス内で、レポートスイートの [内部URLフィルターを設定する必要があります](/help/admin/admin/internal-url-filter-admin.md)。 内部URLフィルターを設定しないと、内部URLが含まれるか、外部URLが表示されない可能性があります。

## Dimension項目

Dimension項目には、訪問者がクリックスルーしてサイトに導くURLが含まれます。 ヒットに転送者データがない場合は、ディメンション項目の下にグループ化され `"Typed/Bookmarked"`ます。 このディメンション項目は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、転送者値がなかったことを意味します。

### 含むDimension項目 `googleusercontent.com`

ユーザーは、ドメインを持つディメンション項目を表示でき `googleusercontent.com`ます。

* **キャッシュされたページ**: Googleのスパイダーは、オフラインになった場合に備えて、常にWebをクロールし、ページのコピーを保存しています。 これらのキャッシュされたページは、「キャッシュ」リンクをクリックすると、ほとんどの検索結果の横に表示されます。 ユーザーがこのリンクをクリックして、Googleがキャッシュしたコンテンツを表示した場合 `webcache.googleusercontent.com` は、通常のディメンション項目です。
* **翻訳済みページ**：Google オファーは、堅牢で便利な翻訳サービスです。このサービスを使用してサイトを表示する場合は、`translate.googleusercontent.com` を起点とします。このディメンション項目は、ユーザーがリンクをクリックして元のコンテンツに戻ると表示されます。
