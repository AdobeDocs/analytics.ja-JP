---
title: クライアントヒント
description: クライアントヒントがデバイス情報のソースとしてユーザーエージェントを徐々に置き換える方法について説明します。
source-git-commit: 788ab49fec9117e0ef2a736f609a627b913b9f8c
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 4%

---


# クライアントヒントの概要と FAQ

クライアントヒントは、ユーザーのデバイスに関する個々の情報です。 これらは、Google Chrome やMicrosoft Edge などの Chromium ブラウザーによって提供されます。 これらのブラウザーでは、クライアントヒントは徐々に User Agent をデバイス情報のソースとして置き換えます。 Adobe Analyticsは、デバイスの参照プロセスを更新し、ユーザーエージェントに加えて、クライアントヒントを使用してデバイス情報を決定します。

Googleでは、ユーザーエージェントのクライアントヒントが次の 2 つのカテゴリに分類されています。低エントロピーと高エントロピーのヒント

* 低エントロピーのヒントは、デバイスに関するより一般的な情報を持っています。 これらのヒントは、Chromium ブラウザーによって自動的に提供されます。

* 高エントロピーのヒントは、より詳細な情報を持っています。 これらのヒントは、リクエストでのみ利用できます。 AppMeasurement と Web SDK の両方を、高エントロピーのヒントをリクエストするように設定できます。 デフォルトでは、両方のライブラリが **not** 高エントロピーのヒントを要求する。

>[!NOTE]
>
>2022 年 10 月より、Chromium ブラウザーの新しいバージョンで、User Agent 文字列で表されるオペレーティングシステムのバージョンを「フリーズ」し始めます。 つまり、時間の経過と共に、User Agent で表されるオペレーティングバージョン情報の正確性が低下します。 オペレーティングシステムのバージョンは高エントロピーのヒントなので、レポートでオペレーティングシステムのバージョンの正確性を維持するには、これらの高エントロピーのヒントを収集するようにコレクションライブラリを設定する必要があります。 時間の経過と共に、User Agent の他のデバイス情報はフリーズし、デバイスのレポートの正確性を維持するためのクライアントヒントが必要になります。

## よくある質問

+++**クライアントヒントのコレクションを有効にする方法を教えてください。**

低エントロピーのヒントは、ブラウザによって自動的に提供され、デバイス情報のAdobeのプロセスに含まれます。 高エントロピーのヒントを収集するように、AppMeasurement（開始 TBD）および Web SDK（開始 TBD）の新しいバージョンを設定できます。 両方のライブラリで、高エントロピーのヒントのコレクションは **デフォルトで無効**. この実装方法の詳細については、こちらを参照してください。

+++

+++**収集する高エントロピーのヒントを選べますか？**

現時点ではありません。 高エントロピーのヒントをすべて収集するか、またはなしを収集するかを選択できます。

+++

+++**Analytics のデバイスレポートに何か変更はありますか？**

レポートに使用できるデバイスフィールドは変更されません。 これらのフィールドに対して取り込まれるデータは、どのフィールドを使用し、クライアントヒントのコレクションを設定したかによって異なる場合があります。

+++

+++**ユーザーエージェントから派生する Analytics レポートフィールドはどれですか？**

* [ブラウザー](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [ブラウザータイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [オペレーティングシステムの種類](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [モバイルデバイスとモバイルデバイスタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)??
* データフィード（これらのフィールドを取り込むには、を更新する必要があります）。 また、依存関係では、デバイス情報と共にモバイル ID を公開できません )。
* Analytics ソースコネクタ（準備ができていません）

+++

+++**高エントロピーのヒントに格納された値から派生する Analytics レポートフィールドはどれですか？**

2022 年 9 月以降、Googleで公開された User-Agent ヒントのフリーズのタイムラインは、2022 年 10 月以降、オペレーティングシステムのバージョンの更新が停止することを示しています。 高エントロピーのヒントがない場合、Analytics の「オペレーティングシステム」ディメンションに含まれるオペレーティングシステムのバージョンの精度は、徐々に低下します。

詳しくは、 [Google発行のタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) ユーザーエージェントがフリーズするタイミングを確認する。

+++

+++**クライアントヒントの影響を受けるブラウザーはどれですか？**

クライアントヒントは、Google Chrome やMicrosoft Edge などの Chromium ブラウザーにのみ適用されます。 他のブラウザーやモバイルアプリからのデータは変更されません。

+++

+++**Adobeがクライアントヒントを使用してデバイス情報を取得する方法**

Adobeは、サードパーティの Device Atlas を使用し、このユーザーは、クライアントヒントとユーザーエージェントの両方を使用してデバイス情報を取得します。

+++

+++**クライアントヒントはデータフィードで使用できますか？**

はい。ドキュメントを参照してください（後述）。

+++

+++**クライアントヒントは、Adobeソースコネクタを介して AEP および CJA に送信されるデータで使用できますか。**

2023 年上半期には、Adobeソースコネクタを介してデータにクライアントヒントを含める予定です。

+++

+++**XDM でクライアントヒントはどのように表されますか？**

詳しくは、 [スキーマドキュメント](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) Adobe Experience Platform

+++

+++**クライアントヒントの詳細はどこで確認できますか？**

この [Googleのブログ投稿](https://web.dev/user-agent-client-hints/) は、参照および開始点として適しています。

+++

+++**様々なヒントフィールドは何ですか？ デバイスレポートに影響するのはどれですか？**

次の表に、2022 年 9 月現在のクライアントヒントを示します。

| ヒント（ヘッダー） | ヒント | 高エントロピーまたは低エントロピー | 例 | Analytics レポートフィールド |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | ブラウザーと重要なバージョン | 低 | Google Chrome 84 | [ブラウザー](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) および [ブラウザーのタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile | モバイルデバイス（true または false） | 低 | TRUE | [モバイルデバイスとモバイルデバイスタイプ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?? |
| Sec-CH-UA-Platform | オペレーティングシステム/プラットフォーム | 低 | Android | [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch | サイトのアーキテクチャ | 高 | &quot;arm&quot; | なし? |
| Sec-CH-UA-Bitness | Sec-CH-UA-Bitness | 高 |  | なし? |
| Sec-CH-UA-Full-Version | ブラウザーの完全なバージョン | 高 | &quot;84.0.4143.2&quot; | なし? |
| Sec-CH-UA-Full-Version-List | ??? | 高 | ??? | なし? |
| Sec-CH-UA-Model | デバイスモデル | 高 | &quot;Pixel 3&quot; | なし? |
| Sec-CH-UA-Platform-Version | オペレーティングシステム/プラットフォームのバージョン | 高 | &quot;10&quot; | [オペレーティングシステム](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++

+++**高エントロピーのヒントを取り込む方法**

高エントロピーのヒントを設定できます

* AppMeasurement を直接使用 [実装ガイドのフラグエントリへのリンク]
* Tags Analytics 拡張機能内
* Web SDK 内。

+++

+++**ユーザーエージェントから削除されるデータは何ですか？また、削除するタイミング**

詳しくは、 [Google発行のタイムライン](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). これは変更される場合があります。

+++