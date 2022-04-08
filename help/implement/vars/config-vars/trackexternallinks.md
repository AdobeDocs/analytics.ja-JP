---
title: trackExternalLinks
description: 出口リンクの自動リンクトラッキングを有効または無効にします。
feature: Variables
exl-id: a34d4ffa-ff82-460e-af7d-1a4be85fc631
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '189'
ht-degree: 100%

---

# trackExternalLinks

アドビでは、各出口リンクに対して [`tl()`](../functions/tl-method.md) メソッドを手動で設定せずに出口リンクを追跡するための機能を提供しています。出口リンクに自動リンクトラッキングを使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はクリックされたリンク URL を [`linkInternalFilters`](linkinternalfilters.md) および [`linkExternalFilters`](linkexternalfilters.md) の値と比較します。一致が見つかった場合、出口リンクトラッキングコールが自動的に実行されます。

## Adobe Experience Platform でタグを使用してアウトバウンドリンクをトラック

「アウトバウンドリンクトラッキング」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. Adobe ID の認証情報を使用して、[データ収集 UI](https://experience.adobe.com/data-collection) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL アウトバウンドリンクトラッキング]」チェックボックスが表示されます。

自動出口リンクトラッキングを有効にするには、このチェックボックスをクリックします。

## AppMeasurement および カスタムコードエディターの s.trackExternalLinks

`s.trackExternalLinks` は、出口リンクの自動トラッキングを有効または無効にするブール値です。アウトバンドリンクを追跡しない場合や、`tl()` メソッドを手動で呼び出して出口リンクを追跡する場合は、この変数を `false` に設定します。

```js
s.trackExternalLinks = true;
```
