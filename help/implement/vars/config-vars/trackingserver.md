---
title: trackingServer
description: イメージリクエストを送信する場所を決定します。
feature: Variables
exl-id: bcc23286-4dd5-45ac-ac6f-7b60e95cb798
role: Admin, Developer
source-git-commit: 284f121428ce9d682b42309dd85cfd117285a7e5
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 52%

---

# trackingServer

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。`trackingServer` 変数は、イメージリクエストが送信される場所を決定します。この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

>[!WARNING]
>
> この値を変更すると、AppMeasurement が別の場所で Cookie を探します。訪問者の Cookie が新しい場所に設定されると、レポートでユニーク訪問者数が一時的に急増する可能性があります。

## Web SDK 拡張機能を使用した Edge ドメイン

Web SDK はを使用します [!UICONTROL Edge ドメイン] トラッキングサーバーとセキュアトラッキングサーバーの両方を処理します。 必要なを設定できます [!UICONTROL Edge ドメイン] web SDK 拡張機能を設定する際の値。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. に移動します [!UICONTROL 拡張機能] タブをクリックしてから、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. 目的のの設定 **[!UICONTROL Edge ドメイン]** テキストフィールド。

参照： [Adobe Experience Platform Web SDK 拡張機能の設定](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja) 詳しくは、Web SDK ドキュメントを参照してください。

>[!TIP]
>
>AppMeasurementまたは Analytics 拡張機能の実装から Web SDK に移行する場合、このフィールドには、に含まれるのと同じ値を使用できます。 `trackingServerSecure` （または `trackingServer`）に設定します。

## Web SDK を手動で実装する Edge ドメイン

SDK の設定に使用 [`edgeDomain`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja). フィールドは、データの送信先のドメインを決定する文字列です。

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

## AppMeasurementの s.trackingServer と Analytics 拡張機能のカスタムコードエディター

`s.trackingServer` 変数は、データを送信する場所を含む文字列です。

## の値を決定する際の考慮事項 `trackingServer`

Adobeのトラッキングサーバードメインを使用するように選択できます（例： `adobedc.net`）を使用するか、sites ドメインに一致するトラッキングサーバーを設定するための特別なプロセスを経ることができます（例： `data.mydomain.com`）、CNAME 実装とも呼ばれます。 サイトドメインに一致するトラッキングサーバーを使用すると、実装の他の側面に応じていくつかの利点があります。 トラッキングサーバーが現在のページのドメインと一致しない場合、AppMeasurementで設定された Cookie はサードパーティとして設定される必要があります。 ブラウザーがサードパーティ cookie をサポートしていない場合、この不一致によって特定の Analytics 機能が妨げられる可能性があります。

- 識別情報の設定：Experience Cloud ID サービスを使用している場合、トラッキングサーバーは Cookie の設定方法に影響を与えません。 ただし、Analytics の従来の識別子（別名 `s_vi` cookie）があり、収集サーバーが現在のドメインと一致しない場合、cookie はサードパーティとして設定する必要があります。 この場合、サードパーティ Cookie がブラウザーでブロックされていると、Analytics はファーストパーティ フォールバック ID （`s_fid`）を使用します `s_vi` cookie。
- 内部リンクでは、リンクトラッキングは機能しません。
- 内部リンクに対しては、Activity Mapは機能しません。
- cookie の確認。

### ファーストパーティ Cookie

ファーストパーティ Cookie の実装を使用する場合、組織内の任意のユーザーが既にファーストパーティ Cookie のプロセスを完了している可能性があります。ファーストパーティ Cookie のプロセスについて詳しくは、『コアサービスユーザーガイド』の [Experience Cloud でのファーストパーティ Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=ja) を参照してください。

実装でファーストパーティ Cookie を初期設定するユーザーも、使用するドメインとサブドメインを定義します。次に例を示します。

```js
s.trackingServer = "data.example.com";
```

### サードパーティのトラッキングサーバー

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
