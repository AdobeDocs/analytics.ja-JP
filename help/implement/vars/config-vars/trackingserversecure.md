---
title: trackingServerSecure
description: HTTPS経由でAdobeにデータを送信するために使用されるドメイン。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
TQID: https://experienceleague.adobe.com/8-M-5apvXuUfQyxdd4Es8Lr5LkgXPK2UNHrhpTzT8xE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 832a3752ab758d573e5b15b2dc38dad120fe8300
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 11%
---
# trackingServerSecure

`trackingServerSecure`変数は、AppMeasurementがHTTPS経由でAdobeにデータを送信するために使用するドメインを決定します。 この変数が正しく定義されていないと、実装でデータ損失が発生する可能性があります。

>[!NOTE]
>
>[`trackingServer`](configuration-variables.md#retired-configuration-variables)はこの変数の廃止されたバリアントです。 HTTP経由で送信されるデータのドメインを指定しました。HTTPSが普及している場合は、代わりに`trackingServerSecure`を使用してください。 `s.trackingServerSecure`が空白の場合、AppMeasurementは`s.trackingServer`値にフォールバックします。

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

[`edgeDomain`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/edgedomain)を使用してSDKを設定します。 フィールドは、データの送信先ドメインを決定する文字列です。

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
// Example value when using a first-party domain
s.trackingServerSecure = "data.example.com";

// Example value when using a third-party domain
s.trackingServerSecure = "example.data.adobedc.net";
```

## `trackingServerSecure`の値を決定するための考慮事項

`trackingServerSecure` （または`edgeDomain`）に使用する値は、組織がAdobeにデータを送信する方法によって異なります。

* **Adobeが管理する証明書プログラム [&#128279;](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/adobe-managed-cert)様、[様が管理する証明書](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/customer-managed-cert)様、[content delivery network （CDN） &#x200B;](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/cdn)様など、1st パーティドメイン**&#x200B;を使用している場合は、その値をドメインに設定します。 &#x200B;例えば、`data.example.com` のように設定します。
* **組織がサードパーティのドメイン**&#x200B;を使用している場合は、値を`data.adobedc.net`のテナント ID サブドメインに設定します。 例えば、`example.data.adobedc.net` のように設定します。

テナント IDの検索方法など、各オプションについて詳しくは、CX Enterprise インターフェイスおよび管理ガイドの「[&#x200B; データ収集ドメインの選択](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/collection-domain)」を参照してください。

Adobeでは、組織全体の一貫性を保つために、この情報を[&#x200B; ソリューション設計ドキュメント &#x200B;](../../prepare/solution-design.md)に保管することを強くお勧めします。

## 訪問者ID サービスまたはExperience Platform ID サービスを使用しない場合の影響

Adobeでは、すべての実装でECIDを訪問者IDの主要な形式として使用することを強くお勧めします。 ECIDの収集は、実装タイプに応じて、いくつかの異なる方法で実装できます。

* AppMeasurementの手動実装では、`VisitorAPI.js`を使用して`getInstance` メソッドを呼び出します。 詳しくは、[Analytics用の訪問者ID サービスの実装](https://experienceleague.adobe.com/ja/docs/id-service/using/implementation/setup-analytics)を参照してください。
* Adobe Analytics タグ拡張機能を使用した実装では、[[!UICONTROL Experience Cloud ID サービス &#x200B;] タグ拡張機能](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/id-service/overview)を使用して、訪問者ID サービスを実装します。 追加設定は不要です。
* 任意の形式のWeb SDK（`alloy.js`またはWeb SDK タグ拡張機能）を使用した実装には、Experience Platform ID サービスが自動的に含まれます。 `edgeDomain`値の設定以外の設定は必要ありません。

**実装でECID**&#x200B;を使用しない場合は、実装に対する次の影響を考慮してください。

* 訪問者ID サービスまたはExperience Platform ID サービスを使用していない場合、`trackingServerSecure`はCookieの場所を判断します。 この変数をサードパーティのドメインに設定すると、ほとんどのモダンなブラウザーがサードパーティのCookieを拒否するため、AppMeasurementではフォールバッククッキーを使用する必要があります。
* 内部リンクトラッキングとActivity Mapの信頼性が低い場合があります。
