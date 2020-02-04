---
title: trackDownloadLinks
description: ダウンロードリンクの自動リンクトラッキングを有効または無効にします。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackDownLoadLinks

アドビでは、各ダウンロードリンクの機能を手動で設定しなくても、ダウンロードリンクを追 `tl()` 跡する機能を提供しています。 ダウンロードリンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurementはクリックされたリンクURLを内の値と比較しま `downloadLinkFileTypes`す。 一致が見つかった場合、ダウンロードリンクトラッキングコールが自動的に実行されます。

## Adobe Experience Platform Launchでのダウンロードリンクの追跡

ダウンロードリンクを追跡は、Adobe Analytics拡張機能を設定する際に [!UICONTROL 、「リンクトラッキング] 」アコーディオンの下にあるチェックボックスです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「リンクトラッキ [!UICONTROL ング] 」アコーディオンを展開すると、「ダウンロードリンクをトラッキング [!UICONTROL 」チェックボックスが表示され] ます。

このチェックボックスをクリックして、自動ダウンロードリンクトラッキングを有効にします。

## AppMeasurementのs.trackDownloadLinksとカスタムコードエディターの起動

は、ダウ `s.trackDownloadLinks` ンロードリンクの自動トラッキングを有効または無効にするブール値です。 ダウンロードリンクを追跡しない場合や、ダウンロードを追跡する関数を手動で呼び出す場 `tl()` 合は、この変数をに設定しま `false`す。

```js
s.trackDownloadLinks = true;
```
