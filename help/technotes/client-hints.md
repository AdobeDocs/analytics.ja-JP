---
title: クライアントヒント
description: クライアントヒントが User-Agent をデバイス情報のソースとして徐々に置き換える方法について説明します。
source-git-commit: f2f1e64a62796b58c24e6ff652db93b21f750669
workflow-type: ht
source-wordcount: '855'
ht-degree: 100%

---


# クライアントヒントの概要とよくある質問

クライアントヒントは、ユーザーのデバイスに関する個々の情報です。 それらは、Google Chrome や Microsoft Edge などの Chromium ブラウザーによって提供されます。これらのブラウザーでは、クライアントヒントは User-Agent をデバイス情報のソースとして徐々に置き換えます。 Adobe Analytics は、User-Agent に加えてクライアントヒントを使用してデバイス情報を決定するように、デバイス検索プロセスをアップデートします。

Google では、User-Agent Client Hints が 2 つのカテゴリ（低エントロピーと高エントロピーのヒント）に分類されています。

* **低エントロピーのヒント**&#x200B;には、デバイスに関するより一般的な情報が含まれています。 Chromium ブラウザーによってこれらのヒントが自動的に提供されます。

* **高エントロピー**&#x200B;ヒントには、より詳細な情報が含まれています。 リクエストがあった場合にのみ、これらのヒントを利用できます。AppMeasurement と Web SDK はどちらも、高エントロピーのヒントをリクエストするように[設定できます](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md)。デフォルトでは、どちらのライブラリも高エントロピーのヒントをリクエスト&#x200B;**しません**。

>[!NOTE]
>
>2022年10月以降、Chromium ブラウザーの新しいバージョンでは、User-Agent 文字列で表されるオペレーティングシステムのバージョンの「フリーズ」が開始されます。ユーザーがデバイスをアップグレードしても、User-Agent のオペレーティングシステムは変更されません。 そのため、時間の経過とともに、User-Agent で表されるオペレーティングバージョン情報の正確性が低下します。オペレーティングシステムのバージョンは高エントロピーのヒントなので、レポートでオペレーティングシステムのバージョンの正確性を維持するには、これらの高エントロピーのヒントを収集するようにコレクションライブラリを設定する必要があります。User-Agent の他のデバイス情報は時間の経過とともにフリーズされ、デバイスレポートの正確性を維持するためにクライアントヒントが必要になります。

## よくある質問

+++**クライアントヒントの詳細はどこで確認できますか？**

この [Google のブログ投稿](https://web.dev/user-agent-client-hints/)は、開始するのに適した資料です。

+++

+++**クライアントヒントのコレクションを有効にするにはどうすればよいですか？**

低エントロピーのヒントはブラウザーによって自動的に提供され、デバイスとブラウザー情報を取得するためのアドビのプロセスに含まれます。新しいバージョンの AppMeasurement（2.23.0 以降）および Web SDK（2.12.0 以降）は、高エントロピーのヒントを収集するように設定できます。どちらのライブラリでも、高エントロピーのヒントの収集は&#x200B;**デフォルトで無効**&#x200B;になっています。

+++

+++**高エントロピーのヒントを取得するにはどうすればよいですか？**

高エントロピーのヒントは、Web SDK および AppMeasurement ライブラリで、それぞれのタグ拡張機能を介して、または collectHighEntropyUserAgentHints フラグを使用して直接設定できます。

+++

+++**収集する高エントロピーのヒントを選択できますか？**

現時点ではできません。高エントロピーのヒントをすべて収集するか、まったく収集しないかを選択できます。

+++

+++**Analytics のデバイスレポートに何か変更はありますか？**

レポートに使用できるデバイスフィールドに変更はありません。これらのフィールドに対して取り込まれるデータは、クライアントヒントの収集を設定するフィールドと方法によって異なる場合があります。

+++

+++**User-Agent から派生する Analytics レポートフィールドはどれですか？**

* [ブラウザー](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=ja)
* [ブラウザータイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=ja)
* [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=ja)
* [オペレーティングシステムの種類](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=ja)
* [モバイルデバイスとモバイルデバイスタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=ja)
* [データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja)

+++

+++**高エントロピーのヒントに格納された値から派生する Analytics レポートフィールドはどれですか？**

2022年9月現在、User-Agent のヒントを「フリーズ」するために Google が公開しているタイムラインによれば、2022年10月以降、オペレーティングシステムのバージョンが更新されなくなります。 ユーザーが OS をアップグレードしても、User-Agent の OS バージョンは更新されません。高エントロピーのヒントがないと、Analytics の「オペレーティングシステム」ディメンションに含まれているオペレーティングシステムバージョンの精度が徐々に低下します。

User-Agent の他の部分がフリーズするタイミングについては、[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。

+++

+++**アドビでは、クライアントヒントをどのように使用してデバイス情報を取得しますか？**

アドビでは、サードパーティの Device Atlas を使用し、クライアントヒントと User-Agent の両方を使用してデバイス情報を取得します。

+++

+++**クライアントヒントの影響を受けるブラウザーはどれですか？**

クライアントヒントは、Google Chrome や Microsoft Edge などの Chromium ブラウザーにのみ適用されます。他のブラウザーやモバイルアプリからのデータは変更されません。

+++

+++**クライアントヒントは、安全でない接続でサポートされていますか？

いいえ。クライアントヒントは、HTTPS などの安全な HTTP 接続を介してのみ収集できます。

+++

+++**クライアントヒントは、Adobe ソースコネクタを介して AEP および CJA に送信されるデータで利用できますか？**

アドビは、2023年上半期に Adobe ソースコネクタを介したデータにクライアントヒントを含める予定です。

+++

+++**クライアントヒントは、XDM でどのように表されますか？**

Adobe Experience Platform の[スキーマドキュメント](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)を参照してください。

+++

+++**様々なヒントフィールドにはどのようなものがありますか？デバイスレポートに影響するのはどれですか？**

2022年9月現在のクライアントヒントを次の表に示します。

| ヒント | 説明 | 高／低エントロピー | 例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | ブラウザーと重要なバージョン | 低 | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | モバイルデバイス（true または false） | 低 | TRUE |
| Sec-CH-UA-Platform | オペレーティングシステム／プラットフォーム | 低 | &quot;Android&quot; |
| Sec-CH-UA-Arch | サイトのアーキテクチャ | 高 | &quot;arm&quot; |
| Sec-CH-UA-Bitness | アーキテクチャのビット数 | 高 | &quot;64&quot; |
| Sec-CH-UA-Full-Version | ブラウザーの完全なバージョン | 高 | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | ブランドとそのバージョンのリスト | 高 | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | デバイスモデル | 高 | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | オペレーティングシステム／プラットフォームのバージョン | 高 | &quot;10&quot; |

+++



+++**User-Agent のどの部分がいつ「フリーズ」されますか？**

[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。これは変更される場合があります。

+++
