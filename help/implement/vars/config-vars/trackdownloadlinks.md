---
title: trackDownloadLinks
description: ダウンロードリンクの自動リンクトラッキングを有効または無効にします。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackDownLoadLinks

アドビでは、各ダウンロードリンクの方法を手動で設定しなくても、ダウンロードリ [`tl()`](../functions/tl-method.md) ンクを追跡する機能を提供しています。 ダウンロードリンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効にすると、AppMeasurementは、クリックされたリンクのURLをの値と比較しま [`linkDownloadFileTypes`](linkdownloadfiletypes.md)す。 一致が見つかった場合、ダウンロードリンクトラッキングコールが自動的に実行されます。

## Adobe Experience Platform Launchでのダウンロードリンクの追跡

ダウンロードリンクを追跡は、Adobe Analyticsの拡張機能を設定する際に、ア [!UICONTROL Link Tracking] コーディオンの下にあるチェックボックスです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオンを展 [!UICONTROL Link Tracking] 開し、チェックボックスを表 [!UICONTROL Track download links] 示します。

チェックボックスをクリックして、自動ダウンロードリンクトラッキングを有効にします。

## AppMeasurementのs.trackDownloadLinksと起動カスタムコードエディター

は、ダウ `s.trackDownloadLinks` ンロードリンクの自動追跡を有効または無効にするブール値です。 ダウンロードリンクを追跡しない場合、またはダウンロードを追跡するメソッドを手動で呼び出す `tl()` 場合は、この変数をに設定しま `false`す。

```js
s.trackDownloadLinks = true;
```
