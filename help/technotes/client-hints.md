---
title: クライアントヒント
description: クライアントヒントが User-Agent をデバイス情報のソースとして徐々に置き換える方法について説明します。
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
feature: Data Configuration and Collection
role: Admin
TQID: https://experienceleague.adobe.com/ewlZMmg1l8tPyF-mrTttQcXgk3Ms4QUwBhSemCgjg90
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1283
ht-degree: 78%

---

# クライアントヒントの概要とよくある質問

クライアントヒントは、ユーザーのデバイスに関する個々の情報です。 それらは、Google Chrome や Microsoft Edge などの Chromium ブラウザーによって提供されます。 これらのブラウザーでは、クライアントヒントは User-Agent をデバイス情報のソースとして徐々に置き換えます。 Adobe Analytics は、User-Agent に加えてクライアントヒントを使用してデバイス情報を決定するように、デバイス検索プロセスをアップデートします。

## 低エントロピーと高エントロピーのクライアントヒント

Google では、User-Agent Client Hints が 2 つのカテゴリ（低エントロピーと高エントロピーのヒント）に分類されています。

* **低エントロピーのヒント**&#x200B;には、デバイスに関するより一般的な情報が含まれています。 Chromium ブラウザーによってこれらのヒントが自動的に提供されます。

* **高エントロピー**&#x200B;ヒントには、より詳細な情報が含まれています。 リクエストがあった場合にのみ、これらのヒントを利用できます。 AppMeasurement と Web SDK はどちらも、高エントロピーのヒントをリクエストするように設定できます。 デフォルトでは、どちらのライブラリも高エントロピーのヒントをリクエスト&#x200B;**しません**。

2022年10月以降、Chromium ブラウザーの新しいバージョンでは、User-Agent 文字列で表されるオペレーティングシステムバージョンの「フリーズ」が開始されました。 オペレーティングシステムのバージョンは高エントロピーのヒントなので、レポートでオペレーティングシステムのバージョンの正確性を維持するには、これらの高エントロピーのヒントを収集するようにコレクションライブラリを設定する必要があります。 User-Agent の他のデバイス情報は時間の経過とともにフリーズされ、デバイスレポートの正確性を維持するためにクライアントヒントが必要になります。

クライアントヒントは、2023年3月2日（PT）にAnalytics デバイスのルックアッププロセスに組み込まれました。 この変更は、AppMeasurementとWeb SDKの両方の実装に適用されます。

Adobe Audience Managerでは、完全な機能を維持するために、高エントロピーのヒントを収集する必要があります。 Adobe Audience Manager](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)への[ サーバーサイド転送を使用している場合は、高エントロピーヒントの収集を有効にすることができます。

## よくある質問

+++**クライアントヒントの詳細はどこで確認できますか？**

この [Google のブログ投稿](https://web.dev/user-agent-client-hints/)は、開始するのに適した資料です。

+++

+++**クライアントヒントのコレクションを有効にするにはどうすればよいですか？**

低エントロピーのヒントはブラウザーから自動的に提供され、デバイスとブラウザーの情報を取得するために取り込まれます。 Web SDK の新しいバージョン（2.12.0 以降）および AppMeasurement（2.23.0 以降）は、それぞれのタグ拡張機能を使用して、または設定オプションを直接使用して、高エントロピーのヒントを収集するように設定できます。 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=ja#enabling-high-entropy-client-hints) および [AppMeasurement](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) の手順を参照してください。

どちらのライブラリでも、高エントロピーのヒントの収集は&#x200B;**デフォルトで無効**&#x200B;になっています。

API で送信されたデータの場合（[Data Insertion API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) や [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) など）、ヒントは、ペイロードに明示的に含める必要があります。 詳しくは、それぞれのドキュメントを参照してください。

+++

+++**収集する高エントロピーのヒントを選択できますか？**

現時点ではできません。 高エントロピーのヒントをすべて収集するか、まったく収集しないかを選択できます。

ブラウザーのメジャーバージョンが低エントロピーのヒントとしてキャプチャされるため、現在fullVersionListは収集されません。

+++

+++**様々なクライアントヒント値にはどのようなものがありますか？**

2022年10月現在のクライアントヒントを次の表に示します。

| ヒント | 説明 | 高／低エントロピー | 例 |
| --- | --- | --- | --- |
| Sec-CH-UA | ブラウザーと重要なバージョン | 低 | `"Google Chrome 84"` |
| Sec-CH-UA-Mobile | モバイルデバイス（true または false） | 低 | `true` |
| Sec-CH-UA-Platform | オペレーティングシステム／プラットフォーム | 低 | `"Android"` |
| 建築 | サイトのアーキテクチャ | 高 | `"arm"` |
| ビット数 | 建築の苦味 | 高 | `"64"` |
| fullVersionList | ブランドとそのバージョンのリスト | 高 | `"Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"` |
| モデル | デバイスモデル | 高 | `"Pixel 3"` |
| platformVersion | オペレーティングシステム／プラットフォームのバージョン | 高 | `"10"` |

* 低エントロピーのヒントは、リクエストヘッダーで収集されます。
* 高エントロピーのヒントは、JavaScript で収集され、クエリ文字列パラメーター値で渡されます。 クエリ文字列パラメーターは、画像リクエストで`h.`をプレフィックスとして使用します。 ブラウザーのメジャーバージョンが低いエントロピーヒントとしてキャプチャされるため、現在fullVersionListは収集されません。

高エントロピーヒントは、JavaScript 呼び出しで収集され、クエリパラメーターで渡されます

+++

+++**Analytics のデバイスレポートに何か変更はありますか？**

レポートに使用できるデバイスフィールドに変更はありません。 これらのフィールドに対して取り込まれるデータは、クライアントヒントの収集を設定するフィールドと方法によって異なる場合があります。

+++

+++**User-Agent から派生する Analytics レポートフィールドはどれですか？**

これらのフィールドは User-Agent から直接得られますが、User-Agent を使用すると、デバイスの詳細に応じて、他のデバイス関連フィールドの値を得ることができます。

* [ブラウザー](/help/components/dimensions/browser.md)
* [ブラウザータイプ](/help/components/dimensions/browser-type.md)
* [オペレーティングシステム](/help/components/dimensions/operating-systems.md)
* [オペレーティングシステムの種類](/help/components/dimensions/operating-system-types.md)
* [モバイルデバイスとモバイルデバイスタイプ](/help/components/dimensions/mobile-dimensions.md)

+++

+++**User-Agent のどの部分がいつ「フリーズ」されますか？** 

[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。 これは変更される場合があります。

+++

+++**Analytics はどのような方法でユーザーエージェントに依存しますか？**

レポートのデバイス情報は、ユーザーエージェントから派生されます。 ユーザーエージェントとクライアントヒントの両方が使用できる場合に、その両方を使用するようにプロセスを更新しました。

フォールバック ID（[s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=ja)）は、ユーザーエージェントおよび IP アドレスから派生されます。 この ID は、cookie を設定できない場合にのみ使用されるので、一般的には使用されていません

+++

+++**高エントロピーのヒントに格納された値から派生する Analytics レポートフィールドはどれですか？**

これは、User-Agent のうち Google によって「凍結」される部分が増えるにつれて、徐々に変化します。 最初に直接影響を受けるフィールドは、オペレーティングシステムのバージョンが含まれる「Operating System」です。User-Agent ヒントの「凍結」に関する Google の公開タイムラインによれば、2022年10月下旬から Chromium バージョン 107 でオペレーティングシステムのバージョンが凍結されます。 その時点で、 User-Agent のオペレーティングシステムバージョンが不正確になる場合があります。

User-Agent の他の部分がフリーズするタイミングについては、[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。

+++

+++**アドビでは、クライアントヒントをどのように使用してデバイス情報を取得しますか？**

アドビでは、サードパーティの Device Atlas を使用していますが、これはクライアントヒントと User-Agent の両方を使用してデバイス情報を取得します。

+++

+++**クライアントヒントの影響を受けるブラウザーはどれですか？**

クライアントヒントは、Google Chrome や Microsoft Edge などの Chromium ブラウザーにのみ適用されます。 他のブラウザーやモバイルアプリからのデータには変更はありません。

+++

+++**クライアントヒントは、安全でない接続でサポートされていますか？**

いいえ。 クライアントヒントは、HTTPS などの安全な HTTP 接続を介してのみ収集できます。

+++

+++**API 送信を使用する際にクライアントヒントのデータを含めるには、どうすればよいですか？**

[一括データ挿入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/) を使用してこれらを含める方法については、ドキュメントを参照してください。

+++

+++**クライアントヒントは、Adobe Source コネクタを介してAdobe Experience PlatformおよびCustomer Journey Analyticsに送信されたデータで利用できますか？**

アドビは、2023年上半期に Adobe ソースコネクタを介したデータにクライアントヒントを含める予定です。

+++

+++**クライアントヒントは、XDM でどのように表されますか？**

Adobe Experience Platform の[スキーマドキュメント](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)を参照してください。

+++

+++**Adobe Audience Manager サーバーサイド転送はクライアントヒントをサポートしますか？** 

はい。 クライアントヒントは、Adobe Audience Managerに転送されるデータに含まれます。 Adobe Audience Managerでは、完全な機能を保持するために、高エントロピーヒントを収集する必要があります。 Adobe Audience Manager](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)への[ サーバーサイド転送を使用している場合は、高エントロピーヒントの収集を有効にすることができます。

+++

+++**ブラウザーのバージョン番号が999.99と表示されるのはなぜですか？**

お客様は、無効なブラウザーまたはデバイスのオペレーティングシステムのバージョン番号（100,000を超える任意の数値）を使用してテストを実行することがあります。 特定の日に無効なブラウザーまたはデバイスのオペレーティングシステムのバージョン番号が大量に発生するのを防ぐために、100,000を超えるバージョン番号はグループ化され、バージョン番号999.99に固定されます。

+++

