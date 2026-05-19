---
title: trackingServerSecure
description: HTTPS経由でAdobeにデータを送信するために使用されるドメイン。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 830
ht-degree: 17%

---

# trackingServerSecure

`trackingServerSecure`変数は、AppMeasurementがHTTPS経由でAdobeにデータを送信するために使用するドメインを決定します。 この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

[Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/ja/docs/id-service/using/home)以前は、この変数はサードパーティ Cookieの設定場所も決定していました。 Adobeでは、可能な限り、すべての実装でID サービスを使用することを強くお勧めします。

## Web SDK拡張機能を使用したEdge ドメイン

Web SDKでは、[!UICONTROL Edge domain]を使用して、Tracking ServerとSecure Tracking Serverの両方を処理します。 Web SDK拡張機能を設定する際に、必要な[!UICONTROL Edge domain]値を設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティを選択します。
1. 「[!UICONTROL 拡張機能]」タブに移動し、[!UICONTROL Adobe Experience Platform Web SDK]の下の「**[!UICONTROL Configure]**」ボタンを選択します。
1. 目的の&#x200B;**[!UICONTROL Edge ドメイン]** テキストフィールドを設定します。

詳しくは、Web SDK ドキュメントの「[Adobe Experience Platform Web SDK拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja)」を参照してください。

>[!TIP]
>
>組織がAppMeasurementまたはAnalytics拡張機能の実装からWeb SDKに移行する場合、このフィールドは`trackingServerSecure` （または`trackingServer`）に含まれる同じ値を使用できます。

## Web SDKを手動で実装するEdge ドメイン

[`edgeDomain`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgedomain)を使用してSDKを設定します。 フィールドは、データの送信先ドメインを決定する文字列です。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## ADOBE ANALYTICS拡張機能を使用したSSL トラッキングサーバー

「[!UICONTROL SSL トラッキングサーバー]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティを選択します。
1. 「[!UICONTROL Extensions]」タブに移動し、「**[!UICONTROL Configure]**」ボタンをAdobe Analyticsの下から選択します。
1. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL SSL トラッキングサーバー]」フィールドが表示されます。

このフィールドが空白のままの場合、デフォルトの値は[!UICONTROL &#x200B; トラッキングサーバー]です。 [!UICONTROL SSL トラッキングサーバー]と[!UICONTROL &#x200B; トラッキングサーバー]の両方が空白の場合、デフォルトは`[rsid].data.adobedc.net`になります。

## AppMeasurementおよびAnalytics拡張機能のカスタムコードエディターのs.trackingServerSecure

`s.trackingServerSecure`変数は、Adobeにデータを送信するドメインを含む文字列です。 これはドメインのみです。プロトコル、パス、ポート、およびスラッシュを省略します。 この変数が空白の場合は、`s.trackingServer`変数の値が使用されます。 `s.trackingServerSecure`と`s.trackingServer`の両方が空白の場合、デフォルトは`[rsid].2o7.net`になります。

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## `trackingServerSecure`の値を決定する際の考慮事項

`trackingServerSecure` （または`edgeDomain`）に使用する値は、いくつかの要因によって異なります。

* [Adobeが管理する証明書プログラム &#x200B;](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/adobe-managed-cert)への参加
* [Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home)が実装され、正しく設定されている場合

**Adobeが管理する証明書プログラム**&#x200B;に参加している場合は、証明書の設定時に選択した1st パーティドメインに値を設定します。 通常、この値は組織が所有するサブドメインです。 例えば、`data.example.com` のように設定します。 組織内のCNAME レコードは、そのデータをAdobeにリダイレクトします。

**証明書プログラム**&#x200B;に参加していない場合は、値を`data.adobedc.net`のサブドメインに設定します。 Adobeでは、一貫性を保つために組織の会社IDを使用することをお勧めします。 例えば、`example.data.adobedc.net` のように設定します。 会社IDを決定するには、次の手順を実行します。

1. Adobe IDの資格情報を使用して[Adobe CX Enterprise](https://experience.adobe.com)にログインします。
1. CX Enterprise インターフェイスの任意の場所で、`[Cmd]` + `[I]` （iOS）または`[Ctrl]` + `[I]` （Windows）を押します。
1. **[!UICONTROL ユーザーデータデバッガー]**&#x200B;が表示されます。 「**[!UICONTROL 割り当てられた組織]**」タブを選択します。
1. 目的のIMS組織を展開します。
1. 「**[!UICONTROL テナント]**」フィールドを探します。 この値は、使用する`data.adobedc.net`の推奨サブドメインです。

>[!NOTE]
>
>`example.data.adobedc.net` より深いサブドメインは使用しないでください。 例えば、`custom.example.data.adobedc.net` が有効なトラッキングサーバーではありません。

古い実装では、`sc.omtrdc.net`や`2o7.net`などの値を持っている場合があります。 これらは主に Adobe Analytics の以前のバージョンで使用されていましたが、現在も有効です。

Adobeでは、組織全体の一貫性を保つために、この情報を[&#x200B; ソリューション設計ドキュメント &#x200B;](../../prepare/solution-design.md)に保管することを強くお勧めします。

## 訪問者ID サービスを使用しない場合の影響

Adobeでは、すべての実装で[Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home)を使用することを強くお勧めします。 ID サービスは、いくつかの異なる方法で実装できます。

* AppMeasurementの手動実装では、`VisitorAPI.js`を使用して`getInstance` メソッドを呼び出します。 詳しくは、[Analytics用Experience Cloud ID サービスの実装](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/setup-analytics)を参照してください。
* Adobe Analytics タグ拡張機能を使用する実装では、[Adobe Experience Cloud ID サービスタグ拡張機能](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview)を使用します。 追加設定は不要です。
* 任意の形式のWeb SDK （`alloy.js`またはWeb SDK タグ拡張機能）を使用する実装では、ID サービスがネイティブにベイク処理されています。 `edgeDomain`値の設定以外の設定は必要ありません。

**実装でID サービスを使用しない場合**&#x200B;は、実装に対して次の影響を考慮してください。

* ID サービスを使用しない場合、`trackingServerSecure`はCookieの場所を決定します。 この変数をサードパーティのドメインに設定すると、ほとんどのモダンなブラウザーがサードパーティのCookieを拒否するため、AppMeasurementではフォールバッククッキーを使用する必要があります。
* 内部リンクトラッキングとActivity Mapの信頼性が低い場合があります。
