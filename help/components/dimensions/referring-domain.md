---
title: 参照ドメイン
description: 訪問者がクリックスルーしてサイトにアクセスする前に閲覧していた最も重要なドメイン。
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 97%

---

# 参照ドメイン

「参照ドメイン」 [ ディメンション ](overview.md) は、訪問者がサイトに到達するためにクリックスルーするドメインがレポートされます。 このディメンションは、どのサードパーティサイトが最もトラフィックを増やしているかを把握するのに役立ちます。ディメンション項目を表示するには、外部サイトにリンクが存在し、訪問者がリンクをクリックする必要があります。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの[内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)を設定する必要があります。内部 URL フィルターを設定しないと、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

同じレポートに、Analysis Workspace と Data Warehouse で異なる結果が表示されます。Analysis Workspace は、内部 URL フィルターに一致する値を除き、個々のページの参照ドメインをレポートします。Data Warehouse は、訪問の最初の参照ドメインのみをレポートし、内部 URL フィルターを無視します。

## このディメンションへのデータ入力

このディメンションには、Analytics インターフェイスでの設定とイメージリクエストでのデータが必要です。

* 実装内で、このディメンションはイメージリクエストの[`r`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `document.referrer` 変数を使用してこのデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外の（API 経由などの）データ収集方法を使用する場合は、イメージリクエストに `r` クエリ文字列パラメーターを必ず含めてください。
* Analytics のインターフェイス内で、レポートスイートの[内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) を設定する必要があります。内部 URL フィルターを設定しないと、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

1 回の訪問での参照ドメインは維持されます。訪問者が 1 回の訪問中に別のドメインのリンクを離れたりクリックしたりした場合、新しい値が更新され、残りの訪問で維持されます。元の値のみを表示したい場合は、「[オリジナルの参照ドメイン](original-referring-domain.md)」を参照してください。

## ディメンション項目

ディメンション項目には、訪問者がサイトにクリックスルーしたドメインが含まれます。ヒットにリファラーデータがない（設定または持続的な）場合は、ディメンション項目 `"Typed/Bookmarked"` でグループ化されます。このディメンション項目は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、リファラー値がなかったことを意味します。`"Typed/Bookmarked"` ディメンション項目は、Analytics に対応しないリダイレクトにも表示されます。  Technotes ユーザーガイドの[リダイレクトとエイリアス](/help/technotes/redirects.md)を参照してください。

### `googleusercontent.com` を含むディメンション項目 

ユーザーは、ドメイン `googleusercontent.com` を持つディメンション項目を表示できます。

* **キャッシュされたページ**：Google のスパイダーは、オフラインになった場合に備えて、常に Web をクロールし、ページのコピーを保存しています。これらのキャッシュされたページは、「キャッシュ」リンクをクリックすると、ほとんどの検索結果の横に表示されます。ユーザーがこのリンクをクリックし、Google がキャッシュしたコンテンツを表示した場合、 `googleusercontent.com` がディメンション項目になります。
* **翻訳済みページ**：Google オファーは、堅牢で便利な翻訳サービスです。このサービスを使用してサイトを表示する場合は、`googleusercontent.com` を起点とします。このディメンション項目は、ユーザーがリンクをクリックして元のコンテンツに戻ると表示されます。
