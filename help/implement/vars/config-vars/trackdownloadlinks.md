---
title: trackDownloadLinks
description: ダウンロードリンクの自動リンクトラッキングを有効または無効にします。
feature: Variables
exl-id: d92f722b-d605-40ad-bb55-ec71219a47e3
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%

---

# trackDownLoadLinks

アドビでは、各ダウンロードリンクに対して [`tl()`](../functions/tl-method.md) メソッドを手動で設定せずにダウンロードリンクを追跡するための機能を提供しています。ダウンロードリンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はクリックされたリンク URL を [`linkDownloadFileTypes`](linkdownloadfiletypes.md) の値と比較します。一致が見つかった場合、ダウンロードリンクトラッキングコールが自動的に実行されます。

## Adobe Experience Platform のタグを使用したダウンロードリンクのトラック

「ダウンロードリンクトラッキング」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL ダウンロードリンクトラッキング]」チェックボックスが表示されます。

自動ダウンロードリンクトラッキングを有効にするには、このチェックボックスをクリックします。

## AppMeasurement および カスタムコードエディターの s.trackDownloadLinks

`s.trackDownloadLinks` は、ダウンロードリンクの自動トラッキングを有効または無効にするブール値です。ダウンロードリンクを追跡しない場合や、`tl()` メソッドを手動で呼び出してダウンロードリンクを追跡する場合は、この変数を `false` に設定します。

```js
s.trackDownloadLinks = true;
```
