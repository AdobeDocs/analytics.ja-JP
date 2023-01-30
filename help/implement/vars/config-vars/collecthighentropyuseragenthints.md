---
title: collectHighEntropyUserAgentHints
description: collectHighEntropyUserAgentHints 変数を使用して、Chromium ブラウザー（Google Chrome や Microsoft Edge など）から高エントロピーヒントをアドビがリクエストするかどうかを決定します。
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
source-git-commit: 5318079d6ad972e66494cd7b7f3bd64359b11012
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 82%

---

# collectHighEntropyUserAgentHints

Adobe Analytics は高エントロピーのクライアントヒントを使用して、デバイスとブラウザーの識別を向上させます。このオプションは、AppMeasurement.js のバージョン2.23.0以降で使用できます。 クライアントヒントについて詳しくは、[この概要と FAQ](/help/technotes/client-hints.md) のほか [Google のブログ](https://web.dev/user-agent-client-hints/)を参照してください。

## Web SDK を使用した高エントロピーヒントの収集

高エントロピーのクライアントヒントは、Web SDK のコンテキストカテゴリの一部です。詳しくは、[Platform Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)を参照してください。

## Adobe Analytics 拡張機能を使用して高エントロピーのヒントを収集する

**[!UICONTROL 高エントロピーのユーザーエージェントヒントを収集]**&#x200B;は、Adobe Analytics 拡張機能を設定する際に表示される一般アコーディオンの下にあるチェックボックスです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/#/@adobepm/data-collection) にログインします。

1. 目的の[!UICONTROL タグプロパティ]をクリックします。

1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」をクリックします。

1. [!UICONTROL 一般]アコーディオンをを展開して、「[!UICONTROL 高エントロピーのユーザーエージェントヒントを収集]」チェックボックスを表示します。デフォルトでは選択解除されています。

## AppMeasurement の collectHighEntropyUserAgentHints

この `s.collectHighEntropyUserAgentHints` 変数は、AppMeasurement が Chromium ブラウザー (Google Chrome やMicrosoft Edge など ) から高エントロピーのヒントをリクエストするかどうかを決定します。 Adobe Analytics はこれらのヒントを使用して、デバイスとブラウザーの識別を向上させます。

次に設定した場合： `true`を指定した場合、高エントロピーのヒントはすべてブラウザーからリクエストされます。

```js
s.collectHighEntropyUserAgentHints = true;
```
