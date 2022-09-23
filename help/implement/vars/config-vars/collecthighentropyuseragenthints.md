---
title: collectHighEntropyUserAgentHints
description: collectHighEntropyUserAgentHints 変数を使用して、Chromium ブラウザー (Google Chrome やMicrosoft Edge など ) から高エントロピーヒントをAdobeがリクエストするかどうかを決定します。
source-git-commit: 0a23ad56a661a420dd44e2875c22927f9734dedf
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---


# collectHighEntropyUserAgentHints

高エントロピーのクライアントヒントは、デバイスとブラウザーの識別を改善するためにAdobe Analyticsで使用されます。 クライアントのヒントについて詳しくは、 [この概要と FAQ](/help/technotes/client-hints.md) 同様に [Googleブログ](https://web.dev/user-agent-client-hints/).

## Web SDK を使用した高エントロピーヒントの収集

高エントロピーのクライアントヒントは、Web SDK のコンテキストカテゴリの一部です。 詳しくは、 [Platform Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) を参照してください。

## Adobe Analytics Extension を使用して高エントロピーのヒントを収集する

**[!UICONTROL 高エントロピーのユーザーエージェントヒントを収集]** は、Adobe Analytics拡張機能を設定する際に「一般」アコーディオンの下にあるチェックボックスです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/@adobepm/data-collection) Adobe ID 資格情報を使用して、

1. 目的の [!UICONTROL タグプロパティ].

1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、「 [!UICONTROL 設定] Adobe Analyticsの

1. を展開します。 [!UICONTROL 一般] アコーディオンは、 [!UICONTROL 高エントロピーのユーザーエージェントヒントを収集] チェックボックスをオンにします。 デフォルトでは選択解除されています。

## AppMeasurement の collectHighEntropyUserAgentHints

この `s.collectHighEntropyUserAgentHints` 変数は、AppMeasurement が Chromium ブラウザー (Google Chrome やMicrosoft Edge など ) から高エントロピーのヒントをリクエストするかどうかを決定します。 これらのヒントは、デバイスとブラウザーの識別を改善するために、Adobe Analyticsで使用されます。

TRUE に設定した場合、高エントロピーのヒントはすべてブラウザから要求されます。

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`