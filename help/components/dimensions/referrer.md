---
title: リファラー
description: 訪問者がクリックスルーしてサイトにアクセスする前にいた URL。
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 48%

---


# リファラー

「リファラー」ディメンションは、クリックスルーしてサイトに到達したときに訪問者が閲覧した URL をレポートします。このディメンションは、どの特定の URL がサイトへのトラフィックを最も多く引き起こしているかを把握するのに役立ちます。ディメンション項目を表示するには、外部URLにリンクが存在し、訪問者がリンクをクリックする必要があります。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの[内部 URL フィルター](/help/admin/admin/internal-url-filter-admin.md)を設定する必要があります。内部 URL フィルターを設定しないと、内部 URL が含まれるか、外部 URL が表示されない可能性があります。

同じレポートに、Analysis WorkspaceとData Warehouseで異なる結果が表示されます。 Analysis Workspaceは、内部URLフィルターに一致する値を除き、個々のページの転送者を報告します。 Data Warehouseは、訪問の最初の転送者のみを報告し、内部URLフィルターを無視します。

## このディメンションへのデータ入力

このディメンションには、Analytics インターフェイスでの設定とイメージリクエストでのデータが必要です。

* 実装内で、このディメンションはイメージリクエストの[`r`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `document.referrer` 変数を使用してこのデータを収集します。変数の上書きを使用して手動で設定できます。 [`referrer`](/help/implement/vars/page-vars/referrer.md) AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外の（API 経由などの）データ収集方法を使用する場合は、クエリリクエストに `r` 文字列パラメーターを必ず含めてください。
* Analytics のインターフェイス内で、レポートスイートの[内部 URL フィルター ](/help/admin/admin/internal-url-filter-admin.md) を設定する必要があります。内部 URL フィルターを設定しないと、内部 URL が含まれるか、外部 URL が表示されない可能性があります。

## Dimension項目

Dimension項目には、訪問者がクリックスルーしてサイトに導くURLが含まれます。 If a hit does not have any referrer data, it groups under the dimension item `"Typed/Bookmarked"`. このディメンション項目は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、転送者値がなかったことを意味します。 ディメンション項目は、Analyticsに対応しないリダイレクトにも表示されます。 `"Typed/Bookmarked"` Technotesユーザーガイドの [リダイレクトとエイリアス](/help/technotes/redirects.md) （英語のみ）を参照してください。

### 含むDimension項目 `googleusercontent.com`

ユーザーは、ドメインを持つディメンション項目を表示でき `googleusercontent.com`ます。

* **キャッシュされたページ**:Googleのスパイダーは、オフラインになった場合に備えて、常にWebをクロールし、ページのコピーを保存しています。 これらのキャッシュされたページは、「キャッシュ」リンクをクリックすると、ほとんどの検索結果の横に表示されます。 ユーザーがこのリンクをクリックして、Googleがキャッシュしたコンテンツを表示した場合 `webcache.googleusercontent.com` は、通常のディメンション項目です。
* **翻訳済みページ**：Google オファーは、堅牢で便利な翻訳サービスです。このサービスを使用してサイトを表示する場合は、`translate.googleusercontent.com` を起点とします。このディメンション項目は、ユーザーがリンクをクリックして元のコンテンツに戻ると表示されます。
