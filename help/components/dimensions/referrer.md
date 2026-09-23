---
title: リファラー
description: 訪問者がクリックスルーしてサイトにアクセスする前にいた URL。
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
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
source-wordcount: '418'
ht-degree: 76%
---
# リファラー

「リファラー」ディメンション [1}は、訪問者がクリックしてサイトに到達した際に使用したURLをレポートします。 ](overview.md)このディメンションは、どの特定の URL がサイトへのトラフィックを最も多く引き起こしているかを把握するのに役立ちます。 ディメンション項目を表示するには、外部 URL にリンクが存在し、訪問者がリンクをクリックする必要があります。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの[内部 URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)を設定する必要があります。 内部 URL フィルターを設定しないと、内部 URL が含まれるか、外部 URL が表示されない可能性があります。

同じレポートに、Analysis Workspace と Data Warehouse で異なる結果が表示されます。 Analysis Workspace は、内部 URL フィルターに一致する値を除き、個々のページのリファラーを報告します。 Data Warehouse は、訪問の最初のリファラーのみを報告し、内部 URL フィルターを無視します。

## このディメンションへのデータ入力

AppMeasurementは、ブラウザーの`document.referrer`値からリファラーを自動的に収集します。 [`referrer`](/help/implement/vars/page-vars/referrer.md) 変数を使用して、収集された値を上書きできます。 また、レポートスイートの[内部URL フィルター](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)を設定する必要があります。設定に失敗すると、内部URLを含めるか、外部URLが表示されない可能性があります。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`referrer`](/help/implement/vars/page-vars/referrer.md) |
| **Web SDK / XDM フィールド** | [`web.webReferrer.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/web-information) |
| **クエリパラメーター** | [`r`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<referrer>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 255 バイト |
| **永続性** | 該当なし |

## ディメンション項目

ディメンション項目には、訪問者がサイトにクリックスルーした URL が含まれます。 ヒットにリファラーデータがない場合は、`"Typed/Bookmarked"` ディメンション項目でグループ化されます。 このディメンション項目は、訪問者がブラウザーのアドレスバーに URL を手動で入力した場合や、ブックマークをクリックした場合など、リファラー値が存在しなかったことを意味します。 `"Typed/Bookmarked"` ディメンション項目は、Analytics に対応しないリダイレクトにも表示されます。 Technotes ユーザーガイドの[リダイレクトとエイリアス](/help/technotes/redirects.md)を参照してください。

### `googleusercontent.com` を含むディメンション項目

ユーザーは、ドメイン `googleusercontent.com` を持つディメンション項目を表示できます。

* **キャッシュされたページ**：Google のスパイダーは、オフラインになった場合に備えて、常に Web をクロールし、ページのコピーを保存しています。 これらのキャッシュされたページは、「キャッシュ」リンクをクリックすると、ほとんどの検索結果の横に表示されます。 ユーザーがこのリンクをクリックし、Google がキャッシュしたコンテンツを表示した場合、 `webcache.googleusercontent.com` は通常のディメンション項目です。
* **翻訳済みページ**：Google オファーは、堅牢で便利な翻訳サービスです。 このサービスを使用してサイトを表示する場合は、`translate.googleusercontent.com` を起点とします。 このディメンション項目は、ユーザーがリンクをクリックして元のコンテンツに戻ると表示されます。
