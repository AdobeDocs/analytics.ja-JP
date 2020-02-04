---
title: trackExternalLinks
description: 離脱リンクの自動リンクトラッキングを有効または無効にします。
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# trackExternalLinks

アドビでは、各離脱リンクの機能を手動で設定しなくても、離脱リンクを追 `tl()` 跡する機能を提供しています。 離脱リンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurementはクリックされたリンクURLをとの値と比 `linkInternalFilters` 較します `linkExternalFilters`。 一致が見つかった場合、離脱リンクトラッキングコールが自動的に実行されます。

## Adobe Experience Platform Launchでのアウトバウンドリンクの追跡

アウトバウンドリンクを追跡は、Adobe Analytics拡張の設定時に [!UICONTROL 、「リンクトラッキング] 」アコーディオンの下にあるチェックボックスです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「リンクトラッキ [!UICONTROL ング] 」アコーディオンを展開すると、「アウトバウンドリンクをトラッ [!UICONTROL キング」チェックボックスが表示されます] 。

離脱リンクの自動追跡を有効にするには、このチェックボックスをクリックします。

## AppMeasurementのs.trackExternalLinksとカスタムコードエディターの起動

は、自 `s.trackExternalLinks` 動離脱リンクトラッキングを有効または無効にするブール値です。 離脱リンクを追跡しない場合、または離脱リンクを追跡する関数を手動で呼び出す場合 `tl()` は、この変数をに設定しま `false`す。

```js
s.trackDownloadLinks = true;
```
