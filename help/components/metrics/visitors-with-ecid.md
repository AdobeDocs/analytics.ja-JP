---
title: Experience Cloud ID を持つ訪問者
description: Adobe Experience Cloud IDサービスを使用している一意の訪問者の数です。
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 19%

---


# Experience Cloud ID を持つ訪問者

「Experience Cloud IDを持つ訪問者」指標は、 [Experience Cloud IDサービスを使用してアドビによって識別された一意の訪問者の数を示します](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)。 このディメンションは、 [](unique-visitors.md) 実訪問者数指標と比較して、サイトへの大部分の訪問者がIDサービスを使用していることを確認するのに役立ちます。 訪問者の大部分がIDサービスcookieを使用していない場合は、導入内の問題を示している可能性があります。

>[!NOTE] この指標は、AdobeターゲットやAdobeオーディエンスマネージャーなど、複数のExperience Cloudサービスを使用する場合のデバッグに特に重要です。 Experience Cloud製品間で共有されるセグメントには、Experience Cloud IDのない訪問者は含まれません。

## この指標の計算方法

この指標は、 [個別訪問者数](unique-visitors.md) 指標に基づきますが、クエリ文字列( `mid`[`s_ecid`](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-analytics.html) cookieに基づく)を使用して識別された個人のみが含まれます。

## Experience Cloud IDの設定のデバッグ

「Experience Cloud IDを持つ訪問者」指標は、Experience Cloud統合のトラブルシューティングや、IDサービスがデプロイされていないサイトの領域の特定に役立ちます。

「Experience Cloud IDを持つ訪問者」を個別訪問者と並べてドラッグして比較します。

![個別訪問者比較](assets/metric-mcvid1.png)

この例では、各ページの「個別訪問者」の数が「Experience Cloud IDを持つ訪問者」の数と同じであることに注意してください。 ただし、実訪問者数の合計数は Experience Cloud ID での訪問者の合計数より大きくなっています。IDサービスが設定されていないページを調べる [計算指標を作成できます](../c-calcmetrics/cm-overview.md) 。 次の定義を使用できます。

![計算指標の定義](assets/metric-mcvid2.png)

この計算指標をレポートに追加することで、MCID を持たない訪問者の数が最も多いページがひとめでわかるように、ページレポートをソートすることができます。

![IDサービスを使用しないページ](assets/metric-mcvid3.png)

「Product Quick表示」ディメンション値は、IDサービスでは正しく実装されないことに注意してください。 組織内の適切なチームと協力して、これらのページを可能な限り早く更新できます。 ブラウザータイプ [、](../dimensions/browser-type.md)サイトセクション [、eVarなど、あらゆるタイプのディメンションを使用して、類似したレポートを作成できます](../dimensions/site-section.md)[](../dimensions/evar.md)。
