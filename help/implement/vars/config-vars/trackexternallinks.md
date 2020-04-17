---
title: trackExternalLinks
description: 出口リンクの自動リンクトラッキングを有効または無効にします。
translation-type: tm+mt
source-git-commit: 94218548dc4e3efd57df95c992003e94640e4330

---


# trackExternalLinks

Adobe offers the ability to track outbound links without manually setting the [`tl()`](../functions/tl-method.md) method for each exit link. 出口リンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はクリックされたリンク URL を [`linkInternalFilters`](linkinternalfilters.md) および [`linkExternalFilters`](linkexternalfilters.md) の値と比較します。一致が見つかった場合、出口リンクトラッキングコールが自動的に実行されます。

## Adobe Experience Platform Launch の「アウトバウンドリンクトラッキング」

Track outbound links is a checkbox under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオンを展 [!UICONTROL Link Tracking] 開し、チェックボックスを表 [!UICONTROL Track outbound links] 示します。

自動出口リンクトラッキングを有効にするには、このチェックボックスをクリックします。

## AppMeasurement および Launch カスタムコードエディターの s.trackExternalLinks

`s.trackExternalLinks` は、出口リンクの自動トラッキングを有効または無効にするブール値です。If you do not want to track outbound links, or would prefer to manually call the `tl()` method to track exit links, set this variable to `false`.

```js
s.trackExternalLinks = true;
```
