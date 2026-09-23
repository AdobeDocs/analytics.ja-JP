---
title: 参照ドメイン
description: 訪問者がクリックスルーして自サイトにアクセスする前に閲覧していた、包括的なドメインを指します。
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 81%
---
# 参照ドメイン

「参照ドメイン」 [ ディメンション ](overview.md)は、訪問者がサイトに到達するためにクリックしたドメインをレポートします。 このディメンションは、どのサードパーティサイトが自サイトへのトラフィックを最も多くもたらしているかを把握するのに役立ちます。 ディメンション項目を表示するには、外部サイトにリンクが存在し、訪問者がリンクをクリックする必要があります。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの[内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)を設定する必要があります。 内部 URL フィルターを設定しないと、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

同じレポートに、Analysis Workspace と Data Warehouse で異なる結果が表示されます。 Analysis Workspace は、内部 URL フィルターに一致する値を除き、個々のページの参照ドメインをレポートします。 Data Warehouse は、訪問の最初の参照ドメインのみをレポートし、内部 URL フィルターを無視します。

## このディメンションへのデータ入力

Adobeは、リファラーURLのドメイン部分を使用して、各ヒットの[ リファラー](referrer.md)からこのディメンションを導き出します。 設定する変数がありません。 レポートスイートの[内部URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)を設定する必要があります。設定に失敗すると、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | なし（リファラーから派生） |
| **Web SDK / XDM フィールド** | なし（リファラーから派生） |
| **クエリパラメーター** | 該当なし |
| **XML タグ** | 該当なし |
| **バイト制限** | 該当なし |
| **永続性** | 訪問 |

アドビは、1 回の訪問に対して参照ドメインを保持します。 訪問者が 1 回の訪問中にサイトを離れ、別のドメイン上のリンクをクリックして戻ってきた場合、新しい値に更新され、その後の訪問中も保持されます。 元の値のみを表示したい場合は、「[オリジナルの参照ドメイン](original-referring-domain.md)」を参照してください。

## ディメンション項目

ディメンション項目には、訪問者がサイトにクリックスルーしたドメインが含まれます。 ヒットにリファラーデータがない（設定または持続的な）場合は、ディメンション項目 `"Typed/Bookmarked"` でグループ化されます。 このディメンション項目は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、リファラー値がなかったことを意味します。 `"Typed/Bookmarked"` ディメンション項目は、Analytics に対応しないリダイレクトにも表示されます。 Technotes ユーザーガイドの[リダイレクトとエイリアス](/help/technotes/redirects.md)を参照してください。

### `googleusercontent.com` を含むディメンション項目

ユーザーは、ドメイン `googleusercontent.com` を持つディメンション項目を表示できます。

* **キャッシュされたページ**：Google のスパイダーは、オフラインになった場合に備えて、常に Web をクロールし、ページのコピーを保存しています。 これらのキャッシュされたページは、「キャッシュ」リンクをクリックすると、ほとんどの検索結果の横に表示されます。 ユーザーがこのリンクをクリックし、Google がキャッシュしたコンテンツを表示した場合、 `googleusercontent.com` がディメンション項目になります。
* **翻訳済みページ**：Google オファーは、堅牢で便利な翻訳サービスです。 このサービスを使用してサイトを表示する場合は、`googleusercontent.com` を起点とします。 このディメンション項目は、ユーザーがリンクをクリックして元のコンテンツに戻ると表示されます。
