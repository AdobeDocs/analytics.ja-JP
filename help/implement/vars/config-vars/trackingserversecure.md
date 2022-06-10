---
title: trackingServerSecure
description: HTTPS ページでイメージリクエストが送信される場所を決定します。
feature: Variables
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 61%

---

# trackingServerSecure

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。`trackingServerSecure` 変数は、イメージリクエストが HTTPS 経由で送信される場所を決定します。また、訪問者の Cookie が保存される場所も決定します。この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

>[!WARNING]
>
> この値を変更すると、AppMeasurement が別の場所で Cookie を探します。訪問者の Cookie が新しい場所に設定されると、レポートでユニーク訪問者数が一時的に急増する可能性があります。

## Web SDK 拡張機能を使用する Edge ドメイン

Web SDK が使用する [!UICONTROL エッジドメイン] を使用して、トラッキングサーバーとセキュアトラッキングサーバーの両方を処理できます。 必要な [!UICONTROL エッジドメイン] 値を指定します。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. 目的のを設定 **[!UICONTROL エッジドメイン]** テキストフィールド。

詳しくは、 [Adobe Experience Platform Web SDK 拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html) （ Web SDK ドキュメント）を参照してください。

>[!TIP]
>
>組織が AppMeasurement または Analytics 拡張機能の実装から Web SDK に移行した場合、このフィールドでは、 `trackingServerSecure` ( または `trackingServer`) をクリックします。

## Web SDK の手動実装の Edge ドメイン

を使用した SDK の設定 [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja). フィールドは、データの送信先のドメインを決定する文字列です。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Adobe Analytics拡張機能を使用した SSL トラッキングサーバー

「[!UICONTROL SSL トラッキングサーバー]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL SSL トラッキングサーバー]」フィールドが表示されます。

このフィールドを空白のままにすると、[`trackingServer`](trackingserver.md) 変数の値がデフォルトになります。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.trackingServerSecure

`s.trackingServerSecure` 変数は、イメージリクエストを送信する場所を含む文字列です。ほとんどの場合、これはサイトのサブドメインです。ブラウザーの最新のプライバシープラクティスによって、一般的なサードパーティ Cookie の信頼性が低下しています。この変数が空白の場合、`s.trackingServer` 変数の値が使用されます。

この変数の値は、ほとんど常に、`data.example.com` などのファーストパーティドメインです。ファーストパーティ Cookie のプロセスについて詳しくは、『コアサービスユーザーガイド』の [Experience Cloud でのファーストパーティ Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja) を参照してください。

実装でファーストパーティ Cookie を初期設定するユーザーも、使用するドメインとサブドメインを定義します。次に例を示します。

```js
s.trackingServerSecure = "data.example.com";
```

CNAME レコードは通常、`data.adobedc.net`、`sc.adobedc.net` または `2o7.net` のサブドメインを指します。
