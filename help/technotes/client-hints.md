---
title: クライアントヒント
description: クライアントヒントが User-Agent をデバイス情報のソースとして徐々に置き換える方法について説明します。
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
feature: Data Configuration and Collection
role: Admin
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 84%

---

# クライアントヒントの概要とよくある質問

クライアントヒントは、ユーザーのデバイスに関する個々の情報です。それらは、Google Chrome や Microsoft Edge などの Chromium ブラウザーによって提供されます。これらのブラウザーでは、クライアントヒントは User-Agent をデバイス情報のソースとして徐々に置き換えます。Adobe Analytics は、User-Agent に加えてクライアントヒントを使用してデバイス情報を決定するように、デバイス検索プロセスをアップデートします。

## 低エントロピーと高エントロピーのクライアントヒント

Google では、User-Agent Client Hints が 2 つのカテゴリ（低エントロピーと高エントロピーのヒント）に分類されています。

* **低エントロピーのヒント**&#x200B;には、デバイスに関するより一般的な情報が含まれています。Chromium ブラウザーによってこれらのヒントが自動的に提供されます。

* **高エントロピー**&#x200B;ヒントには、より詳細な情報が含まれています。リクエストがあった場合にのみ、これらのヒントを利用できます。AppMeasurement と Web SDK はどちらも、高エントロピーのヒントをリクエストするように設定できます。デフォルトでは、どちらのライブラリも高エントロピーのヒントをリクエスト&#x200B;**しません**。

2022年10月以降、Chromium ブラウザーの新しいバージョンでは、User-Agent 文字列で表されるオペレーティングシステムバージョンの「フリーズ」が開始されました。オペレーティングシステムのバージョンは高エントロピーのヒントなので、レポートでオペレーティングシステムのバージョンの正確性を維持するには、これらの高エントロピーのヒントを収集するようにコレクションライブラリを設定する必要があります。User-Agent の他のデバイス情報は時間の経過とともにフリーズされ、デバイスレポートの正確性を維持するためにクライアントヒントが必要になります。

クライアントヒントは、2023 年 2 月 27 日（PT）以降、2023 年 3 月 2 日（PT）まで、Analytics デバイス検索プロセスに組み込まれます。 現在、AppMeasurement と Web SDK の両方でヒントデータの収集がサポートされていますが、2月中旬まではデバイス検索では使用されません。後述のように、オペレーティングシステムのバージョンは 10月よりフリーズされていますが、段階的なロールアウトおよび多くのユーザーエージェントが既にフローズン OS バージョンを提供しているという事実（詳しくは、[こちら](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=ja)を参照）により、アドビでは、これが影響するのは Chrome 訪問者の 3％未満と見積もっています。

>[!NOTE]
>
> 2023年1月の時点で、Mac および Windows オペレーティング システムの一部のバージョンがユーザーエージェントで正しく表示されず、高エントロピーのクライアントヒントでは正しく表示されます。詳しくは、[オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=ja)を参照してください。

Adobe Audience Managerでは、機能を完全に保持するために、高エントロピーのヒントを収集する必要があります。 Adobe Audience Managerへの [ サーバーサイド転送 ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=ja) を使用している場合は、高エントロピーヒントの収集を有効にした方がよいでしょう。

## よくある質問

+++**クライアントヒントの詳細はどこで確認できますか？**

この [Google のブログ投稿](https://web.dev/user-agent-client-hints/)は、開始するのに適した資料です。

+++

+++**クライアントヒントのコレクションを有効にするにはどうすればよいですか？**

低エントロピーのヒントはブラウザーから自動的に提供され、デバイスとブラウザーの情報を取得するために取り込まれます。Web SDK の新しいバージョン（2.12.0 以降）および AppMeasurement（2.23.0 以降）は、それぞれのタグ拡張機能を使用して、または設定オプションを直接使用して、高エントロピーのヒントを収集するように設定できます。[Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=ja#enabling-high-entropy-client-hints) および [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html?lang=ja) の手順を参照してください。

どちらのライブラリでも、高エントロピーのヒントの収集は&#x200B;**デフォルトで無効**&#x200B;になっています。

API で送信されたデータの場合（[Data Insertion API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-insertion/) や [Bulk Data Insertion API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) など）、ヒントは、ペイロードに明示的に含める必要があります。詳しくは、それぞれのドキュメントを参照してください。

+++

+++**収集する高エントロピーのヒントを選択できますか？**

現時点ではできません。高エントロピーのヒントをすべて収集するか、まったく収集しないかを選択できます。

ブラウザーのメジャーバージョンは低エントロピーのヒントとしてキャプチャされるので、fullVersionList は現在収集されないことに注意してください。

+++

+++**様々なクライアントヒント値にはどのようなものがありますか？**

2022年10月現在のクライアントヒントを次の表に示します。

| ヒント | 説明 | 高／低エントロピー | 例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | ブラウザーと重要なバージョン | 低 | `"Google Chrome 84"` |
| Sec-CH-UA-Mobile | モバイルデバイス（true または false） | 低 | `true` |
| Sec-CH-UA-Platform | オペレーティングシステム／プラットフォーム | 低 | `"Android"` |
| architecture | サイトのアーキテクチャ | 高 | `"arm"` |
| ビット | アーキテクチャのビット数 | 高 | `"64"` |
| fullVersionList | ブランドとそのバージョンのリスト | 高 | `"Not A;Brand";v="99", "Chromium";v="98", "Google Chrome";v="98"` |
| model | デバイスモデル | 高 | `"Pixel 3"` |
| platformVersion | オペレーティングシステム／プラットフォームのバージョン | 高 | `"10"` |

* 低エントロピーのヒントは、リクエストヘッダーで収集されます。
* 高エントロピーのヒントは、JavaScript で収集され、クエリ文字列パラメーター値で渡されます。クエリ文字列パラメーターは、`h.` をイメージリクエストのプレフィックスとして使用します。 ブラウザーのメジャーバージョンは低エントロピーのヒントとしてキャプチャされるので、fullVersionList は現在収集されないことに注意してください。

高エントロピーヒントは、JavaScript 呼び出しで収集され、クエリパラメーターで渡されます

+++

+++**Analytics のデバイスレポートに何か変更はありますか？**

レポートに使用できるデバイスフィールドに変更はありません。これらのフィールドに対して取り込まれるデータは、クライアントヒントの収集を設定するフィールドと方法によって異なる場合があります。

+++

+++**User-Agent から派生する Analytics レポートフィールドはどれですか？**

これらのフィールドは User-Agent から直接得られますが、User-Agent を使用すると、デバイスの詳細に応じて、他のデバイス関連フィールドの値を得ることができます。

* [ブラウザー](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=ja)
* [ブラウザータイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=ja)
* [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=ja)
* [オペレーティングシステムの種類](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=ja)
* [モバイルデバイスとモバイルデバイスタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=ja)

+++

+++**User-Agent のどの部分がいつ「フリーズ」されますか？**

[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。これは変更される場合があります。

+++

+++**Analytics はどのような方法でユーザーエージェントに依存しますか？**

レポートのデバイス情報は、ユーザーエージェントから派生されます。ユーザーエージェントとクライアントヒントの両方が使用できる場合に、その両方を使用するようにプロセスを更新しました。

フォールバック ID（[s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=ja)）は、ユーザーエージェントおよび IP アドレスから派生されます。この ID は、cookie を設定できない場合にのみ使用されるので、一般的には使用されていません

+++

+++**高エントロピーのヒントに格納された値から派生する Analytics レポートフィールドはどれですか？**

これは、User-Agent のうち Google によって「凍結」される部分が増えるにつれて、徐々に変化します。最初に直接影響を受けるフィールドは、オペレーティングシステムのバージョンが含まれる「Operating System」です。User-Agent ヒントの「凍結」に関する Google の公開タイムラインによれば、2022年10月下旬から Chromium バージョン 107 でオペレーティングシステムのバージョンが凍結されます。その時点で、 User-Agent のオペレーティングシステムバージョンが不正確になる場合があります。

User-Agent の他の部分がフリーズするタイミングについては、[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。

+++

+++**アドビでは、クライアントヒントをどのように使用してデバイス情報を取得しますか？**

アドビでは、サードパーティの Device Atlas を使用していますが、これはクライアントヒントと User-Agent の両方を使用してデバイス情報を取得します。

+++

+++**クライアントヒントの影響を受けるブラウザーはどれですか？**

クライアントヒントは、Google Chrome や Microsoft Edge などの Chromium ブラウザーにのみ適用されます。他のブラウザーやモバイルアプリからのデータには変更はありません。

+++

+++**クライアントヒントは、安全でない接続でサポートされていますか？**

いいえ。クライアントヒントは、HTTPS などの安全な HTTP 接続を介してのみ収集できます。

+++

+++**API 送信を使用する際にクライアントヒントのデータを含めるには、どうすればよいですか？**

[一括データ挿入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/) を使用してこれらを含める方法については、ドキュメントを参照してください。

+++

+++**クライアントヒントは、Adobe Source Connector を介してAdobe Experience PlatformおよびCustomer Journey Analyticsに送信されるデータで利用できますか？**

アドビは、2023年上半期に Adobe ソースコネクタを介したデータにクライアントヒントを含める予定です。

+++

+++**クライアントヒントは、XDM でどのように表されますか？**

Adobe Experience Platform の[スキーマドキュメント](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)を参照してください。

+++

+++**Adobe Audience Manager サーバーサイド転送はクライアントヒントをサポートしますか？**

はい。クライアントヒントは、Adobe Audience Managerに転送されるデータに含まれます。 なお、Adobe Audience Managerでは、機能を完全に保持するために、高エントロピーのヒントを収集する必要があります。 Adobe Audience Managerへの [ サーバーサイド転送 ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=ja) を使用している場合は、高エントロピーヒントの収集を有効にした方がよいでしょう。

+++
