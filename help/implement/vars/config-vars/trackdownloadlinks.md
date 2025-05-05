---
title: trackDownloadLinks
description: ダウンロードリンクの自動リンクトラッキングを有効または無効にします。
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 59%

---

# trackDownLoadLinks

アドビでは、各ダウンロードリンクに対して [`tl()`](../functions/tl-method.md) メソッドを手動で設定せずにダウンロードリンクを追跡するための機能を提供しています。ダウンロードリンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はクリックされたリンク URL を [`linkDownloadFileTypes`](linkdownloadfiletypes.md) の値と比較します。一致が見つかった場合、ダウンロードリンクトラッキングコールが自動的に実行されます。

## Web SDK 拡張機能を使用したクリック収集の有効化または無効化

Web SDK を設定する際は、「[!UICONTROL &#x200B; クリックデータ収集を有効にする &#x200B;]」チェックボックスを使用します。 このチェックボックスでは、離脱リンクとダウンロードリンクの両方を処理します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL &#x200B; 拡張機能 &#x200B;]」タブに移動し、「&lbrace;4 **[!UICONTROL Adobe Experience Platform Web SDK]」の下にある「設定** ボタンをクリックします。
1. [!UICONTROL &#x200B; データ収集 &#x200B;] で、「**[!UICONTROL クリックデータ収集を有効にする]**」チェックボックスをクリックします。

## Web SDK を手動で実装して、クリック収集を有効または無効にします

[`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled) を使用して SDK を設定します。 フィールドは、リンククリックに関連付けられたデータを自動的に収集するかどうかを決定するブール値です。 デフォルト値は `true` です。自動リンクトラッキングを無効にする場合、この値を `false` に設定します。 この設定では、ダウンロードリンクと離脱リンクの両方の自動リンクトラッキングを処理します。

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Adobe Analytics拡張機能を使用したダウンロードリンクのトラッキング

「ダウンロードリンクトラッキング」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL ダウンロードリンクトラッキング]」チェックボックスが表示されます。

自動ダウンロードリンクトラッキングを有効にするには、このチェックボックスをクリックします。

## AppMeasurementーおよび Analytics 拡張機能のカスタムコードエディターの s.trackDownloadLinks

`s.trackDownloadLinks` は、ダウンロードリンクの自動トラッキングを有効または無効にするブール値です。ダウンロードリンクを追跡しない場合や、`tl()` メソッドを手動で呼び出してダウンロードリンクを追跡する場合は、この変数を `false` に設定します。

```js
s.trackDownloadLinks = true;
```
