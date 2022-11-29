---
title: クライアントヒント
description: クライアントヒントが User-Agent をデバイス情報のソースとして徐々に置き換える方法について説明します。
exl-id: e0a74daa-12a2-4999-9920-2636b061dcc8
source-git-commit: f80430a4537b17991a0c2cf104df47a053c3792d
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 88%

---

# クライアントヒントの概要とよくある質問

クライアントヒントは、ユーザーのデバイスに関する個々の情報です。 それらは、Google Chrome や Microsoft Edge などの Chromium ブラウザーによって提供されます。これらのブラウザーでは、クライアントヒントは User-Agent をデバイス情報のソースとして徐々に置き換えます。 Adobe Analytics は、User-Agent に加えてクライアントヒントを使用してデバイス情報を決定するように、デバイス検索プロセスをアップデートします。

Google では、User-Agent Client Hints が 2 つのカテゴリ（低エントロピーと高エントロピーのヒント）に分類されています。

* **低エントロピーのヒント**&#x200B;には、デバイスに関するより一般的な情報が含まれています。 Chromium ブラウザーによってこれらのヒントが自動的に提供されます。

* **高エントロピー**&#x200B;ヒントには、より詳細な情報が含まれています。 リクエストがあった場合にのみ、これらのヒントを利用できます。AppMeasurement と Web SDK はどちらも、高エントロピーのヒントをリクエストするように設定できます。デフォルトでは、どちらのライブラリも高エントロピーのヒントをリクエスト&#x200B;**しません**。

>[!NOTE]
>
>クライアントヒントは、2023年1月中旬以降、Analytics デバイス検索プロセスに組み込まれます。 現在、AppMeasurement と Web SDK の両方でヒントデータの収集がサポートされていますが、1 月中旬まではデバイス検索では使用されません。 これは、年末の重要な時期にレポートが中断される可能性を避けるためです。 下記のオペレーティングシステムのバージョンは 10 月から凍結されますが、この凍結が徐々に展開され、ほとんどのユーザーエージェントが正しい OS バージョンに固定されるので、この影響を受ける Chrome 訪問者は 3％未満と推定されます。

>[!NOTE]
>
>2022年10月以降、Chromium ブラウザーの新しいバージョンでは、User-Agent 文字列で表されるオペレーティングシステムバージョンの「フリーズ」が開始されます。オペレーティングシステムのバージョンは高エントロピーのヒントなので、レポートでオペレーティングシステムのバージョンの正確性を維持するには、これらの高エントロピーのヒントを収集するようにコレクションライブラリを設定する必要があります。User-Agent の他のデバイス情報は時間の経過とともにフリーズされ、デバイスレポートの正確性を維持するためにクライアントヒントが必要になります。

>[!NOTE]
>
>AAM では、機能を完全に保持するために、高エントロピーのヒントを収集する必要があります。 [AAM へのサーバーサイド転送](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=ja)を使用している場合は、高エントロピーヒントの収集を有効にした方がよいでしょう。

## よくある質問

+++**クライアントヒントの詳細はどこで確認できますか？**

この [Google のブログ投稿](https://web.dev/user-agent-client-hints/)は、開始するのに適した資料です。

+++

+++**クライアントヒントのコレクションを有効にするにはどうすればよいですか？**

低エントロピーのヒントはブラウザーから自動的に提供され、デバイスとブラウザーの情報を取得するために取り込まれます。Web SDK の新しいバージョン（2.12.0 以降）および AppMeasurement（2.23.0 以降）は、それぞれのタグ拡張機能を使用して、または設定オプションを直接使用して、高エントロピーのヒントを収集するように設定できます。 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html#enabling-high-entropy-client-hints) および [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html) の手順を参照してください。

どちらのライブラリでも、高エントロピーのヒントの収集は&#x200B;**デフォルトで無効**&#x200B;になっています。

+++

+++**収集する高エントロピーのヒントを選択できますか？**

現時点ではできません。高エントロピーのヒントをすべて収集するか、まったく収集しないかを選択できます。

+++

+++**様々なクライアントヒント値にはどのようなものがありますか？**

2022年10月現在のクライアントヒントを次の表に示します。

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

これらのフィールドは User-Agent から直接得られますが、User-Agent を使用すると、デバイスの詳細に応じて、他のデバイス関連フィールドの値を得ることができます。

* [ブラウザー](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html)
* [ブラウザータイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html)
* [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html)
* [オペレーティングシステムの種類](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html)
* [モバイルデバイスとモバイルデバイスタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html)

+++

+++**User-Agent のどの部分がいつ「フリーズ」されますか？**

[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。これは変更される場合があります。

+++

+++**Analytics はユーザーエージェントにどのように依存しますか。**

レポートのデバイス情報は、ユーザーエージェントから取得されます。 ユーザーエージェントとクライアントヒントの両方を利用できる場合は、プロセスを更新しました。

フォールバック ID ([s_fid](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/analytics-ids.html?lang=en)) は、ユーザーエージェントと IP アドレスから派生します。 この ID は、Cookie を設定できない場合にのみ使用されるので、広く使用されていません

+++

+++**高エントロピーのヒントに格納された値から派生する Analytics レポートフィールドはどれですか？**

これは、User-Agent のうち Google によって「凍結」される部分が増えるにつれて、徐々に変化します。 最初に直接影響を受けるフィールドは、オペレーティングシステムのバージョンが含まれる「Operating System」です。 User-Agent ヒントの「凍結」に関する Google の公開タイムラインによれば、2022年10月下旬から Chromium バージョン 107 でオペレーティングシステムのバージョンが凍結されます。 その時点で、 User-Agent のオペレーティングシステムバージョンが不正確になる場合があります。

User-Agent の他の部分がフリーズするタイミングについては、[Google が公開しているタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)を参照してください。

+++

+++**アドビでは、クライアントヒントをどのように使用してデバイス情報を取得しますか？**

Adobeは、サードパーティの Device Atlas を使用し、クライアントのヒントとユーザーエージェントの両方を使用してデバイス情報を取得します。

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

+++**クライアントヒントは、Adobe ソースコネクタを介して AEP および CJA に送信されるデータで利用できますか？**

アドビは、2023年上半期に Adobe ソースコネクタを介したデータにクライアントヒントを含める予定です。

+++

+++**クライアントヒントは、XDM でどのように表されますか？**

Adobe Experience Platform の[スキーマドキュメント](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)を参照してください。

+++

+++**AAM サーバーサイド転送はクライアントヒントをサポートしますか？**

はい。クライアントヒントは、AAM に転送されるデータに含まれます。なお、AAM では、完全な機能を維持するために、高エントロピーのヒントを収集する必要があります。 [AAM へのサーバーサイド転送](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html)を使用している場合は、高エントロピーヒントの収集を有効にした方がよいでしょう。

+++
