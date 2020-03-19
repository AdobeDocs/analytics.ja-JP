---
title: trackExternalLinks
description: 離脱リンクの自動リンクトラッキングを有効または無効にします。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackExternalLinks

アドビでは、離脱リンクごとに手動で方法を設定しなくても、離脱リンクを [`tl()`](../functions/tl-method.md) 追跡する機能を提供しています。 離脱リンクの自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効にすると、AppMeasurementは、クリックされたリンクURLをとの値と比較 [`linkInternalFilters`](linkinternalfilters.md) しま [`linkExternalFilters`](linkexternalfilters.md)す。 一致が見つかった場合、離脱リンクトラッキングコールが自動的に実行されます。

## Adobe Experience Platform Launchでのアウトバウンドリンクの追跡

アウトバウンドリンクを追跡は、Adobe Analyticsの拡張機能を設定する際に、ア [!UICONTROL Link Tracking] コーディオンの下にあるチェックボックスです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオンを展 [!UICONTROL Link Tracking] 開し、チェックボックスを表 [!UICONTROL Track outbound links] 示します。

離脱リンクの自動追跡を有効にするには、このチェックボックスをクリックします。

## AppMeasurementのs.trackExternalLinksとカスタムコードエディターの起動

は、離脱 `s.trackExternalLinks` リンクの自動追跡を有効または無効にするブール値です。 離脱リンクを追跡しない場合、または離脱リンクを追跡するメソッドを手動で呼び出す `tl()` 場合は、この変数をに設定しま `false`す。

```js
s.trackDownloadLinks = true;
```
