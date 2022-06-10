---
title: trackDownloadLinks
description: ダウンロードリンクの自動リンクトラッキングを有効または無効にします。
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 51%

---

# trackDownLoadLinks

アドビでは、各ダウンロードリンクに対して [`tl()`](../functions/tl-method.md) メソッドを手動で設定せずにダウンロードリンクを追跡するための機能を提供しています。ダウンロードリンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はクリックされたリンク URL を [`linkDownloadFileTypes`](linkdownloadfiletypes.md) の値と比較します。一致が見つかった場合、ダウンロードリンクトラッキングコールが自動的に実行されます。

## Web SDK 拡張機能を使用したクリックコレクションの有効化または無効化

以下を使用： [!UICONTROL クリックデータ収集を有効にする] 」チェックボックスをオンにします。 このチェックボックスは、出口リンクとダウンロードリンクの両方を処理します。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 次に移動： [!UICONTROL 拡張機能] 「 」タブで、 **[!UICONTROL 設定]** 下のボタン [!UICONTROL Adobe Experience Platform Web SDK].
1. の下 [!UICONTROL データ収集]、 **[!UICONTROL クリックデータ収集を有効にする]** チェックボックス。

## Web SDK を手動で実装するクリックコレクションを有効または無効にします

を使用した SDK の設定 [`clickCollectionEnabled`](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html#clickCollectionEnabled). 「 」フィールドは、リンククリックに関連付けられたデータを自動的に収集するかどうかを決定するブール値です。 デフォルト値は `true` です。この値をに設定します。 `false` 自動リンクトラッキングを無効にする場合。 この設定は、ダウンロードリンクと出口リンクの両方に対する自動リンクトラッキングを処理します。

```json
alloy("configure", {
  "clickCollectionEnabled": true
});
```

## Adobe Analytics拡張機能を使用してダウンロードリンクを追跡する

「ダウンロードリンクトラッキング」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL ダウンロードリンクトラッキング]」チェックボックスが表示されます。

自動ダウンロードリンクトラッキングを有効にするには、このチェックボックスをクリックします。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.trackDownloadLinks

`s.trackDownloadLinks` は、ダウンロードリンクの自動トラッキングを有効または無効にするブール値です。ダウンロードリンクを追跡しない場合や、`tl()` メソッドを手動で呼び出してダウンロードリンクを追跡する場合は、この変数を `false` に設定します。

```js
s.trackDownloadLinks = true;
```
