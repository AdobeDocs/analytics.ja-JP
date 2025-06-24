---
title: trackingServerSecure
description: HTTPS ページでイメージリクエストが送信される場所を決定します。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 66%

---

# trackingServerSecure

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。`trackingServerSecure` 変数は、イメージリクエストが HTTPS 経由で送信される場所を決定します。また、訪問者の Cookie が保存される場所も決定します。この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

>[!WARNING]
>
> この値を変更すると、AppMeasurement が別の場所で Cookie を探します。訪問者の Cookie が新しい場所に設定されると、レポートでユニーク訪問者数が一時的に急増する可能性があります。

## Web SDK拡張機能を使用したEdge ドメイン

Web SDKでは、[!UICONTROL Edge ドメイン &#x200B;] を使用して、トラッキングサーバーとセキュアトラッキングサーバーの両方を処理します。 Web SDK拡張機能を設定する際に、目的の 0&rbrace;Edge ドメイン &rbrace; 値を設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」タブに移動し、「&lbrace;4 **[!UICONTROL Adobe Experience Platform Web SDK]」の下にある「設定** ボタンをクリックします。
1. 目的の「**[!UICONTROL Edge ドメイン]**」テキストフィールドを設定します。

詳しくは、Web SDK ドキュメントの [Adobe Experience Platform Web SDK拡張機能の設定 ](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja) を参照してください。

>[!TIP]
>
>AppMeasurementまたは Analytics 拡張機能の実装から Web SDKに移行する場合、このフィールドには `trackingServerSecure` （または `trackingServer`）に含まれるのと同じ値を使用できます。

## Web SDKを手動で実装するEdge ドメイン

[`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja) を使用したSDKの設定 フィールドは、データの送信先のドメインを決定する文字列です。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Adobe Analytics拡張機能を使用した SSL トラッキングサーバー

「[!UICONTROL SSL トラッキングサーバー]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL SSL トラッキングサーバー]」フィールドが表示されます。

このフィールドを空白のままにすると、[`trackingServer`](trackingserver.md) 変数の値がデフォルトになります。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.trackingServerSecure

`s.trackingServerSecure` 変数は、イメージリクエストを送信する場所を含む文字列です。ほとんどの場合、これはサイトのサブドメインです。ブラウザーの最新のプライバシープラクティスによって、一般的なサードパーティ Cookie の信頼性が低下しています。この変数が空白の場合、`s.trackingServer` 変数の値が使用されます。

この変数の値は、ほとんど常に、`data.example.com` などのファーストパーティドメインです。ファーストパーティ Cookie のプロセスについて詳しくは、『コアサービスユーザーガイド』の [Experience Cloud でのファーストパーティ Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja) を参照してください。

実装でファーストパーティ Cookie を初期設定するユーザーも、使用するドメインとサブドメインを定義します。次に例を示します。

```js
s.trackingServerSecure = "data.example.com";
```

CNAME レコードは通常、`data.adobedc.net`、`sc.adobedc.net` または `2o7.net` のサブドメインを指します。
