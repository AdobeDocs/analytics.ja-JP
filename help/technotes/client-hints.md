---
title: クライアントヒント
description: クライアントヒントが User-Agent をデバイス情報のソースとして徐々に置き換える方法について説明します。
source-git-commit: 1bd34bd2bdbe5ad8abb75be81554837e53c112fb
workflow-type: tm+mt
source-wordcount: '948'
ht-degree: 75%

---


# クライアントヒントの概要とよくある質問

クライアントヒントは、ユーザーのデバイスに関する個々の情報です。 それらは、Google Chrome や Microsoft Edge などの Chromium ブラウザーによって提供されます。これらのブラウザーでは、クライアントヒントは User-Agent をデバイス情報のソースとして徐々に置き換えます。 Adobe Analytics は、User-Agent に加えてクライアントヒントを使用してデバイス情報を決定するように、デバイス検索プロセスをアップデートします。

Google では、User-Agent Client Hints が 2 つのカテゴリ（低エントロピーと高エントロピーのヒント）に分類されています。

* **低エントロピーのヒント**&#x200B;には、デバイスに関するより一般的な情報が含まれています。 Chromium ブラウザーによってこれらのヒントが自動的に提供されます。

* **高エントロピー**&#x200B;ヒントには、より詳細な情報が含まれています。 リクエストがあった場合にのみ、これらのヒントを利用できます。AppMeasurement と Web SDK はどちらも、高エントロピーのヒントをリクエストするように[設定できます](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md)。デフォルトでは、どちらのライブラリも高エントロピーのヒントをリクエスト&#x200B;**しません**。

>[!NOTE]
>
>2022年10月以降、Chromium ブラウザーの新しいバージョンでは、User-Agent 文字列で表されるオペレーティングシステムのバージョンの「フリーズ」が開始されます。オペレーティングシステムのバージョンは高エントロピーのヒントなので、レポートでオペレーティングシステムのバージョンの正確性を維持するには、これらの高エントロピーのヒントを収集するようにコレクションライブラリを設定する必要があります。User-Agent の他のデバイス情報は時間の経過とともにフリーズされ、デバイスレポートの正確性を維持するためにクライアントヒントが必要になります。

>[!NOTE]
>
>AAMでは、機能を完全に保持するために、高エントロピーのヒントを収集する必要があります。 次を使用する場合： [AAMへのサーバー側転送](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=ja) 次に、高エントロピーのヒントの収集を有効にする場合があります。

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

+++**様々なクライアントヒント値は何ですか？**

次の表に、2022 年 10 月現在のクライアントヒントを示します。

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

+++**Analytics のデバイスレポートに何か変更はありますか？**

レポートに使用できるデバイスフィールドに変更はありません。これらのフィールドに対して取り込まれるデータは、クライアントヒントの収集を設定するフィールドと方法によって異なる場合があります。

+++

+++**User-Agent から派生する Analytics レポートフィールドはどれですか？**

これらのフィールドは User-Agent から直接派生しますが、User-Agent を使用して、デバイスの詳細に応じて、他のデバイス関連フィールドの値を導き出すことができます。

* [ブラウザー](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=ja)
* [ブラウザータイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=ja)
* [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=ja)
* [オペレーティングシステムの種類](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=ja)
* [モバイルデバイスとモバイルデバイスタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=ja)

+++

+++**高エントロピーのヒントに格納された値から派生する Analytics レポートフィールドはどれですか？**

これは、Googleが User Agent のより多くの部分を「フリーズ」すると、時間の経過と共に変化します。 最初に直接影響を受けるのは、オペレーティングシステムのバージョンを含む「オペレーティングシステム」です。 「凍結」User-Agent のヒントに関するGoogleの公開タイムラインに従い、2022 年 10 月後半から Chromium バージョン 107 でオペレーティングシステムのバージョンが凍結されます。 その時点で、ユーザーエージェントのオペレーティングシステムのバージョンが不正確になる場合があります。

User-Agent の他の部分がフリーズするタイミングについては、[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。

+++

+++**アドビでは、クライアントヒントをどのように使用してデバイス情報を取得しますか？**

Adobeは、サードパーティの Device Atlas を使用し、クライアントヒントと User-Agent の両方を使用してデバイス情報を取得します。

+++

+++**クライアントヒントの影響を受けるブラウザーはどれですか？**

クライアントヒントは、Google Chrome やMicrosoft Edge などの Chromium ブラウザーにのみ適用されます。 他のブラウザーやモバイルアプリからのデータは変更されません。

+++

+++**クライアントヒントは、安全でない接続を介してサポートされていますか？**

いいえ。クライアントヒントは、HTTPS などの安全な HTTP 接続を介してのみ収集できます。

+++

+++**クライアントヒントは、Adobe ソースコネクタを介して AEP および CJA に送信されるデータで利用できますか？**

アドビは、2023年上半期に Adobe ソースコネクタを介したデータにクライアントヒントを含める予定です。

+++

+++**クライアントヒントは、XDM でどのように表されますか？**

Adobe Experience Platform の[スキーマドキュメント](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)を参照してください。

+++

+++**User-Agent のどの部分がいつ「フリーズ」されますか？**

[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。これは変更される場合があります。

+++

+++**AAMサーバー側転送はクライアントヒントをサポートしますか？**

はい。クライアントヒントは、AAMに転送されるデータに含まれます。 AAMでは、機能を完全に維持するために、高エントロピーのヒントを収集する必要があることに注意してください。 次を使用する場合： [AAMへのサーバー側転送](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 次に、高エントロピーのヒントの収集を有効にすることができます。

+++

