---
title: collectHighEntropyUserAgentHints
description: collectHighEntropyUserAgentHints 変数を使用して、Chromium ブラウザー（Google Chrome や Microsoft Edge など）から高エントロピーヒントをアドビがリクエストするかどうかを決定します。
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/SfKPGVjuEsMzJUVJYSEh9M8eawg0RqLNceSlqrTu3Ps'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 100%

---

# collectHighEntropyUserAgentHints

Adobe Analytics は高エントロピーのクライアントヒントを使用して、デバイスとブラウザーの識別を向上させます。 このオプションは、AppMeasurement.js のバージョン 2.23.0 以降で使用できます。 クライアントヒントについて詳しくは、[この概要と FAQ](/help/technotes/client-hints.md) のほか [Google のブログ](https://web.dev/user-agent-client-hints/)を参照してください。

## Web SDK を使用した高エントロピーヒントの収集

高エントロピーのクライアントヒントは、Web SDK のコンテキストカテゴリの一部です。 詳しくは、[Platform Web SDK の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja)を参照してください。

## Adobe Analytics 拡張機能を使用して高エントロピーのヒントを収集する

**[!UICONTROL 高エントロピーのユーザーエージェントヒントを収集]**&#x200B;は、Adobe Analytics 拡張機能を設定する際に表示される一般アコーディオンの下にあるチェックボックスです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/#/@adobepm/data-collection) にログインします。
1. 目的の[!UICONTROL タグプロパティ]をクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」をクリックします。
1. [!UICONTROL 一般]アコーディオンをを展開して、「[!UICONTROL 高エントロピーのユーザーエージェントヒントを収集]」チェックボックスを表示します。 デフォルトでは選択解除されています。

## AppMeasurement の collectHighEntropyUserAgentHints

`s.collectHighEntropyUserAgentHints` 変数は、AppMeasurement が Chromium ブラウザー（Google Chrome や Microsoft Edge など）から高エントロピーのヒントをリクエストするかどうかを決定します。 Adobe Analytics はこれらのヒントを使用して、デバイスとブラウザーの識別を向上させます。

`true` に設定すると、すべての高エントロピーのヒントがブラウザーからリクエストされます。

```js
s.collectHighEntropyUserAgentHints = true;
```
