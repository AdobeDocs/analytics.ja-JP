---
title: trackingServer
description: イメージリクエストを送信する場所を決定します。
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 72%

---

# trackingServer

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。`trackingServer` 変数は、イメージリクエストが送信される場所を決定します。この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

>[!WARNING]
>
> この値を変更すると、AppMeasurement が別の場所で Cookie を探します。訪問者の Cookie が新しい場所に設定されると、レポートでユニーク訪問者数が一時的に急増する可能性があります。

## Web SDK 拡張機能を使用する Edge ドメイン

Web SDK が使用する [!UICONTROL Edge ドメイン] を使用して、トラッキングサーバーとセキュアトラッキングサーバーの両方を処理できます。 必要に応じて [!UICONTROL Edge ドメイン] の値を指定します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. 目的のを設定 **[!UICONTROL Edge ドメイン]** テキストフィールド。

詳しくは、 [Adobe Experience Platform Web SDK 拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja) （ Web SDK ドキュメント）を参照してください。

>[!TIP]
>
>組織がAppMeasurementまたは Analytics 拡張機能の実装から Web SDK に移行した場合、このフィールドでは、 `trackingServerSecure` ( または `trackingServer`) をクリックします。

## Web SDK の手動実装の Edge ドメイン

を使用した SDK の設定 [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja). フィールドは、データの送信先のドメインを決定する文字列です。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Adobe Analytics拡張機能を使用したトラッキングサーバー

「トラッキングサーバー」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL トラッキングサーバー]」フィールドが表示されます。

このフィールドを空白のままにすると、デフォルトでは `[rsid].data.adobedc.net` になります。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.trackingServer

`s.trackingServer` 変数は、データを送信する場所を含む文字列です。

## の値を決定 `trackingServer`

この変数の値は、ファーストパーティ Cookie とサードパーティ Cookie のどちらを使用するかによって異なります。実装にファーストパーティ Cookie を使用することを強くお勧めします。

### ファーストパーティ Cookie

ファーストパーティ Cookie の実装を使用する場合、組織内の任意のユーザーが既にファーストパーティ Cookie のプロセスを完了している可能性があります。ファーストパーティ Cookie のプロセスについて詳しくは、『コアサービスユーザーガイド』の [Experience Cloud でのファーストパーティ Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja) を参照してください。

実装でファーストパーティ Cookie を初期設定するユーザーも、使用するドメインとサブドメインを定義します。次に例を示します。

```js
s.trackingServer = "data.example.com";
```

### サードパーティ Cookie

>[!TIP]
>
>最新のブラウザーではプライバシー保護が強化されており、サードパーティ Cookie の信頼性が低下しています。ファーストパーティ Cookie のワークフローに従うことをお勧めします。

サードパーティ Cookie の実装を使用する場合、`trackingServer` の値は `data.adobedc.net` のサブドメインになります。次に例を示します。

```js
s.trackingServer = "example.data.adobedc.net";
```

Adobe Analytics を使用する別の組織では採用されないような、組織に固有のサブドメインを選択します。組織に割り当てられた訪問者名前空間を推奨します。  組織内のすべての実装で同じトラッキングサーバーを使用していることを確認します。[ソリューション設計ドキュメント](../../prepare/solution-design.md)でこの情報を維持すると役立つ場合があります。

組織が既に、`sc.omtrdc.net`ドメインまたは `2o7.net`ドメインのサードパーティトラッキングサーバーを使用している可能性があります。  これらは主に Adobe Analytics の以前のバージョンで使用されていましたが、現在も有効です。

>[!NOTE]
>
> `example.data.adobedc.net` より深いサブドメインは使用しないでください。例えば、`custom.example.data.adobedc.net` が有効なトラッキングサーバーではありません。
