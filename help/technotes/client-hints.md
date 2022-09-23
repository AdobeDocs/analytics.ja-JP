---
title: クライアントヒント
description: クライアントのヒントが User-Agent をデバイス情報のソースとして徐々に置き換える方法について説明します。
source-git-commit: cd8370f6c19e79e1a8a506e772db390708e96a44
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---


# クライアントヒントの概要と FAQ

クライアントヒントは、ユーザーのデバイスに関する個々の情報です。 これらは、Google Chrome やMicrosoft Edge などの Chromium ブラウザーによって提供されます。 これらのブラウザでは、クライアントヒントは User-Agent をデバイス情報のソースとして徐々に置き換えます。 Adobe Analyticsは、User-Agent に加えてクライアントヒントを使用してデバイス情報を決定するように、デバイス参照プロセスを更新します。

Googleでは、User-Agent クライアントのヒントが次の 2 つのカテゴリに分類されています。低エントロピーと高エントロピーのヒント

* 低エントロピーのヒントは、デバイスに関するより一般的な情報を持っています。 これらのヒントは、Chromium ブラウザーによって自動的に提供されます。

* 高エントロピーのヒントは、より詳細な情報を持っています。 これらのヒントは、リクエストでのみ利用できます。 AppMeasurement と Web SDK の両方を、高エントロピーのヒントをリクエストするように設定できます。 デフォルトでは、両方のライブラリが **not** 高エントロピーのヒントを要求する。

>[!NOTE]
>
>2022 年 10 月より、Chromium ブラウザーの新しいバージョンで、User-Agent 文字列で表されるオペレーティングシステムのバージョンの「フリーズ」が開始されます。 ユーザーがデバイスをアップグレードしても、User-Agent のオペレーティングシステムは変更されません。 したがって、User-Agent で表されるオペレーティングバージョン情報の正確性が低下します。 オペレーティングシステムのバージョンは高エントロピーのヒントなので、レポートでオペレーティングシステムのバージョンの正確性を維持するには、これらの高エントロピーのヒントを収集するようにコレクションライブラリを設定する必要があります。 User-Agent の他のデバイス情報は時間が経つにつれてフリーズし、デバイスのレポートの正確性を維持するためのクライアントヒントが必要になります。

## よくある質問

+++**クライアントヒントの詳細はどこで確認できますか？**

この [Googleのブログ投稿](https://web.dev/user-agent-client-hints/) は、参照および開始点として適しています。

+++

+++**クライアントヒントのコレクションを有効にする方法を教えてください。**

低エントロピーのヒントは、ブラウザによって自動的に提供され、デバイスおよびブラウザ情報を導出するAdobeのプロセスに含まれます。 高エントロピーのヒントを収集するように、AppMeasurement の新しいバージョン (2.23.0以降 ) および Web SDK(2.12.0以降 ) を設定できます。 両方のライブラリで、高エントロピーのヒントのコレクションは **デフォルトで無効**.

+++

+++**高エントロピーのヒントを取り込む方法**

高エントロピーのヒントは、Web SDK および AppMeasurement ライブラリで、それぞれのタグ拡張機能を使用して設定するか、collectHighEntropyUserAgentHints フラグを使用して直接設定できます。

+++

+++**収集する高エントロピーのヒントを選べますか？**

現時点ではありません。 高エントロピーのヒントをすべて収集するか、またはなしを収集するかを選択できます。

+++

+++**Analytics のデバイスレポートに何か変更はありますか？**

レポートに使用できるデバイスフィールドは変更されません。 これらのフィールドに対して取り込まれるデータは、どのフィールドを使用し、クライアントヒント用にコレクションを設定したかによって異なる場合があります。

+++

+++**User-Agent から派生する Analytics レポートフィールドはどれですか？**

* [ブラウザー](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [ブラウザータイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [オペレーティングシステムの種類](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [モバイルデバイスとモバイルデバイスタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)
* [データフィード](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=ja)

+++

+++**高エントロピーのヒントに格納された値から派生する Analytics レポートフィールドはどれですか？**

2022 年 9 月以降、Googleが「凍結」User-Agent のヒントに関する公開されたタイムラインは、2022 年 10 月以降、オペレーティングシステムのバージョンの更新が停止されることを示しています。 ユーザーが OS をアップグレードしても、User-Agent の OS バージョンは更新されません。 高エントロピーのヒントがない場合、Analytics の「オペレーティングシステム」ディメンションに含まれるオペレーティングシステムのバージョンの精度は、徐々に低下します。

詳しくは、 [Google発行のタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) ユーザエージェントの他の部分が凍結するタイミングを確認する。

+++

+++**Adobeがクライアントヒントを使用してデバイス情報を取得する方法**

Adobeは、サードパーティの Device Atlas を使用し、このユーザーはクライアントのヒントと User-Agent の両方を使用してデバイス情報を取得します。

+++

+++**クライアントヒントの影響を受けるブラウザーはどれですか？**

クライアントヒントは、Google Chrome やMicrosoft Edge などの Chromium ブラウザーにのみ適用されます。 他のブラウザーやモバイルアプリからのデータは変更されません。

+++

+++**クライアントヒントは、Adobeソースコネクタを介して AEP および CJA に送信されるデータで使用できますか。**

2023 年上半期には、Adobeソースコネクタを介してデータにクライアントヒントを含める予定です。

+++

+++**XDM でクライアントヒントはどのように表されますか？**

詳しくは、 [スキーマドキュメント](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) Adobe Experience Platform

+++

+++**様々なヒントフィールドは何ですか？ デバイスレポートに影響するのはどれですか？**

次の表に、2022 年 9 月現在のクライアントヒントを示します。

| ヒント | 説明 | 高エントロピーまたは低エントロピー | 例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | ブラウザーと重要なバージョン | 低 | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | モバイルデバイス（true または false） | 低 | TRUE |
| Sec-CH-UA-Platform | オペレーティングシステム/プラットフォーム | 低 | &quot;Android&quot; |
| Sec-CH-UA-Arch | サイトのアーキテクチャ | 高 | &quot;arm&quot; |
| Sec-CH-UA-Bitness | アーキテクチャビット | 高 | &quot;64&quot; |
| Sec-CH-UA-Full-Version | ブラウザーの完全なバージョン | 高 | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | ブランドとバージョンのリスト | 高 | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | デバイスモデル | 高 | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | オペレーティングシステム/プラットフォームのバージョン | 高 | &quot;10&quot; |

+++



+++**User-Agent のどの部分が「フリーズ」され、いつフリーズされますか。**

詳しくは、 [Google発行のタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). これは変更される場合があります。

+++
