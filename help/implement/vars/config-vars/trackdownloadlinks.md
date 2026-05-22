---
title: trackDownloadLinks
description: ダウンロードリンクの自動リンクトラッキングを有効または無効にします。
feature: Appmeasurement Implementation
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/mH9olBbVVqz9WCBCWiZuDe9JcljL0ADOesKSfEE6gkA'
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
source-wordcount: 352
ht-degree: 49%

---

# trackDownloadLinks

アドビでは、各ダウンロードリンクに対して [`tl()`](../functions/tl-method.md) メソッドを手動で設定せずにダウンロードリンクを追跡するための機能を提供しています。 ダウンロードリンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はクリックされたリンク URL を [`linkDownloadFileTypes`](linkdownloadfiletypes.md) の値と比較します。 一致が見つかった場合、ダウンロードリンクトラッキングコールが自動的に実行されます。

## Web SDK拡張機能を使用したクリック収集の有効化または無効化

Web SDKの設定時に「[!UICONTROL &#x200B; クリックデータ収集を有効にする]」チェックボックスを使用します。 このチェックボックスは、離脱リンクとダウンロードリンクの両方を処理します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. [!UICONTROL 拡張機能] タブに移動し、[!UICONTROL Adobe Experience Platform Web SDK]の下にある&#x200B;**[!UICONTROL Configure]** ボタンをクリックします。
1. [!UICONTROL &#x200B; データ収集]で、「**[!UICONTROL クリックデータ収集を有効にする]**」チェックボックスをクリックします。

## Web SDKを手動で実装するクリック収集を有効または無効にする

[`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=ja#clickCollectionEnabled)を使用してSDKを設定します。 このフィールドは、リンククリックに関連するデータが自動的に収集されるかどうかを決定するブール値です。 デフォルト値は `true` です。 自動リンクトラッキングを無効にする場合は、この値を`false`に設定します。 この設定は、ダウンロード リンクと終了リンクの両方の自動リンク トラッキングを処理します。

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Adobe Analytics拡張機能を使用してダウンロードリンクを追跡する

「ダウンロードリンクトラッキング」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL ダウンロードリンクトラッキング]」チェックボックスが表示されます。

自動ダウンロードリンクトラッキングを有効にするには、このチェックボックスをクリックします。

## AppMeasurementのs.trackDownloadLinksとAnalytics拡張機能のカスタムコードエディター

`s.trackDownloadLinks` は、ダウンロードリンクの自動トラッキングを有効または無効にするブール値です。 ダウンロードリンクを追跡しない場合、または手動で`tl()` メソッドを呼び出してダウンロードを追跡する場合は、この変数を`false`に設定します。 自動的なダウンロードリンクのトラッキングを機能させるには、変数[linkDownloadFileTypes](linkdownloadfiletypes.md)も設定する必要があります。

```js
s.trackDownloadLinks = true;
```
