---
title: trackingServerSecure
description: HTTPS 経由でAdobeにデータを送信するために使用されるドメイン。
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7918b18e73618368543a996ca121b64b7afb33ab
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 13%

---

# trackingServerSecure

`trackingServerSecure` 変数は、AppMeasurementが HTTPS でAdobeにデータを送信するために使用するドメインを決定します。 この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

[Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home) より前は、この変数もサードパーティ Cookie が設定された場所を特定していました。 Adobeでは、可能な限り、すべての実装で ID サービスを使用することを強くお勧めします。

## Web SDK拡張機能を使用したEdge ドメイン

Web SDKでは、[!UICONTROL Edge ドメイン &#x200B;] を使用して、トラッキングサーバーとセキュアトラッキングサーバーの両方を処理します。 Web SDK拡張機能を設定する際に、目的の [!UICONTROL 0&rbrace;Edge ドメイン &rbrace; 値を設定できます。]

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティを選択します。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」タブに移動し、「**[!UICONTROL Adobe Experience Platform Web SDK]**」の下にある「設定 [!UICONTROL &#x200B; ボタンを選択し &#x200B;] す。
1. 目的の「**[!UICONTROL Edge ドメイン]**」テキストフィールドを設定します。

詳しくは、Web SDK ドキュメントの [Adobe Experience Platform Web SDK拡張機能の設定 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=ja) を参照してください。

>[!TIP]
>
>AppMeasurementまたは Analytics 拡張機能の実装から Web SDKに移行する場合、このフィールドには `trackingServerSecure` （または `trackingServer`）に含まれるのと同じ値を使用できます。

## Web SDKを手動で実装するEdge ドメイン

[`edgeDomain`](https://experienceleague.adobe.com/ja/docs/experience-platform/web-sdk/commands/configure/edgedomain) を使用したSDKの設定 フィールドは、データの送信先のドメインを決定する文字列です。

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Adobe Analytics拡張機能を使用した SSL トラッキングサーバー

「[!UICONTROL SSL トラッキングサーバー]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL 一般]」アコーディオンの下にあるフィールドです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティを選択します。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」タブに移動し、「Adobe Analytics」の下にある **[!UICONTROL 設定]** ボタンを選択します。
1. 「[!UICONTROL 一般]」アコーディオンを展開すると、「[!UICONTROL SSL トラッキングサーバー]」フィールドが表示されます。

このフィールドを空白のままにした場合、デフォルトで [!UICONTROL &#x200B; トラッキングサーバー &#x200B;] の値になります。 [!UICONTROL SSL トラッキングサーバー &#x200B;] と [!UICONTROL &#x200B; トラッキングサーバー &#x200B;] の両方が空の場合、デフォルトでは `[rsid].data.adobedc.net` になります。

## AppMeasurementおよび Analytics 拡張機能のカスタムコードエディターの s.trackingServerSecure

`s.trackingServerSecure` 変数は、Adobeにデータを送信するためのドメインを含む文字列です。 これはドメインのみであり、protocol、path、port、および slashes を省略します。 この変数が空の場合、`s.trackingServer` 変数の値が使用されます。 `s.trackingServerSecure` と `s.trackingServer` の両方が空白の場合は、デフォルトで `[rsid].2o7.net` になります。

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## `trackingServerSecure` の値を決定する際の考慮事項

`trackingServerSecure` （または `edgeDomain`）に使用する値は、次のいくつかの要因によって異なります。

* [Adobeが管理する証明書プログラムへの参加 &#x200B;](https://experienceleague.adobe.com/ja/docs/core-services/interface/data-collection/adobe-managed-cert)
* [Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home) を実装しており、正しくセットアップされている場合

**組織がAdobe管理の証明書プログラムに参加している場合**、証明書の設定時に選択したファーストパーティドメインに値を設定します。 通常、この値は組織が所有するサブドメインです。 例えば、`data.example.com` のように設定します。組織内の CNAME レコードは、そのデータをAdobeにリダイレクトします。

**証明書プログラムに参加していない場合**、値を `data.adobedc.net` のサブドメインに設定します。 Adobeでは、一貫性を保つため、組織の会社 ID を使用することをお勧めします。 例えば、`example.data.adobedc.net` のように設定します。以下の手順を使用して、会社 ID を決定します。

1. Adobe IDの資格情報を使用して [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Experience Cloud インターフェイスの任意の場所で、`[Cmd]` + `[I]` （iOS）または `[Ctrl]` + `[I]` （Windows）を押します。
1. **[!UICONTROL ユーザーデータデバッガー]** が表示されます。 「**[!UICONTROL 割り当てられた組織]**」タブを選択します。
1. 目的の IMS 組織を展開します。
1. 「**[!UICONTROL テナント]**」フィールドを見つけます。 この値は、使用する `data.adobedc.net` の推奨サブドメインです。

>[!NOTE]
>
> `example.data.adobedc.net` より深いサブドメインは使用しないでください。例えば、`custom.example.data.adobedc.net` が有効なトラッキングサーバーではありません。

古い実装には、`sc.omtrdc.net` や `2o7.net` などの値が含まれている場合があります。 これらは主に Adobe Analytics の以前のバージョンで使用されていましたが、現在も有効です。

Adobeでは、組織全体で一貫性を保つため、この情報を [&#x200B; ソリューションデザインドキュメント &#x200B;](../../prepare/solution-design.md) で管理することを強くお勧めします。

## 訪問者 ID サービスを使用しない場合の影響

Adobeでは、すべての実装で [Adobe Experience Cloud ID サービス &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/home) を使用することを強くお勧めします。 ID サービスは、様々な方法で実装できます。

* 手動のAppMeasurement実装では `VisitorAPI.js` を使用して `getInstance` メソッドを呼び出します。 詳しくは、[Analytics 用のExperience Cloud Identity Service の実装 &#x200B;](https://experienceleague.adobe.com/ja/docs/id-service/using/implementation/setup-analytics) を参照してください。
* Adobe Analytics タグ拡張機能を使用した実装では、[Adobe Experience Cloud ID サービスタグ拡張機能 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/extensions/client/id-service/overview) を使用します。 追加後は、追加の設定は必要ありません。
* 任意の形式の Web SDK（`alloy.js` または Web SDK タグ拡張機能）を使用している実装では、ID サービスをネイティブにベイク処理しています。 `edgeDomain` 値を設定する以外に、設定は必要ありません。

**実装で ID サービスを使用しない場合**、実装に対する次の影響を考慮してください。

* ID サービスを使用していない場合、`trackingServerSecure` は Cookie の場所を決定します。 ほとんどのブラウザーがサードパーティ cookie を拒否しているので、この変数をサードパーティドメインに設定すると、AppMeasurementではフォールバック cookie を使用します。
* 内部リンクトラッキングとActivity Mapの信頼性が低下する可能性があります。
