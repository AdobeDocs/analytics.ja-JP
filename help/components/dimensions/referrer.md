---
title: リファラー
description: 訪問者がクリックスルーしてサイトにアクセスする前にいた URL。
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 97%

---


# リファラー

「リファラー」ディメンションは、クリックスルーしてサイトに到達したときに訪問者が閲覧した URL をレポートします。このディメンションは、どの特定の URL がサイトへのトラフィックを最も多く引き起こしているかを把握するのに役立ちます。ディメンション項目を表示するには、外部 URL にリンクが存在し、訪問者がリンクをクリックする必要があります。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの[内部 URL フィルター](/help/admin/admin/internal-url-filter-admin.md)を設定する必要があります。内部 URL フィルターを設定しないと、内部 URL が含まれるか、外部 URL が表示されない可能性があります。

同じレポートに、Analysis Workspace と Data Warehouse で異なる結果が表示されます。Analysis Workspace は、内部 URL フィルターに一致する値を除き、個々のページの転送者を報告します。Data Warehouse は、訪問の最初の転送者のみを報告し、内部 URL フィルターを無視します。

## このディメンションへのデータ入力

このディメンションには、Analytics インターフェイスでの設定とイメージリクエストでのデータが必要です。

* 実装内で、このディメンションはイメージリクエストの[`r`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `document.referrer` 変数を使用してこのデータを収集します。変数の上書きを使用して手動で設定できます。 [`referrer`](/help/implement/vars/page-vars/referrer.md) AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外の（API 経由などの）データ収集方法を使用する場合は、クエリリクエストに `r` 文字列パラメーターを必ず含めてください。
* Analytics のインターフェイス内で、レポートスイートの[内部 URL フィルター](/help/admin/admin/internal-url-filter-admin.md) を設定する必要があります。内部 URL フィルターを設定しないと、内部 URL が含まれるか、外部 URL が表示されない可能性があります。

## ディメンション項目

ディメンション項目には、訪問者がサイトにクリックスルーしたドメインが含まれます。ヒットにリファラーデータがない場合は、`"Typed/Bookmarked"` ディメンション項目でグループ化されます。このディメンション項目は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、リファラー値がなかったことを意味します。`"Typed/Bookmarked"` ディメンション項目は、Analytics に対応しないリダイレクトにも表示されます。  Technotes ユーザーガイドの[リダイレクトとエイリアス](/help/technotes/redirects.md)を参照してください。

### `googleusercontent.com` を含むディメンション項目 

ユーザーは、ドメイン `googleusercontent.com` を持つディメンション項目を表示できます。

* **キャッシュされたページ**：Google のスパイダーは、オフラインになった場合に備えて、常に Web をクロールし、ページのコピーを保存しています。これらのキャッシュされたページは、「キャッシュ」リンクをクリックすると、ほとんどの検索結果の横に表示されます。ユーザーがこのリンクをクリックし、Google がキャッシュしたコンテンツを表示した場合、 `webcache.googleusercontent.com` は通常のディメンション項目です。
* **翻訳済みページ**：Google オファーは、堅牢で便利な翻訳サービスです。このサービスを使用してサイトを表示する場合は、`translate.googleusercontent.com` を起点とします。このディメンション項目は、ユーザーがリンクをクリックして元のコンテンツに戻ると表示されます。
