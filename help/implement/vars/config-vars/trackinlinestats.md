---
title: trackInlineStats
description: 実装で Activity Map を有効または無効にします。
keywords: Activity Map を無効にする
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 78%

---

# trackInlineStats

Activity Map は、訪問者がクリックした場所とクリックした内容に関するデータを収集する、Adobe Analytics の機能です。このデータは、Analytics レポートで表示することも、ブラウザー拡張機能オーバーレイを使用して表示することもできます。Activity Map 機能を使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はリンクに関する情報を収集し、そのデータを次のイメージリクエストに送信します。各クリックからの情報は、「`s_sq`」Cookie に保存されます。

## Web SDK を使用したActivity Map

Web SDK は、Activity Mapのデータ収集をまだサポートしていません。

## Adobe Analytics拡張機能を使用した Clickmap の有効化

「[!UICONTROL Clickmap の有効化]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL Clickmap の有効化]」チェックボックスが表示されます。

チェックボックスをクリックして、Activity Map のトラッキングを有効にします。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.trackInlineStats

`s.trackInlineStats`は、Activity Map のトラッキングを有効または無効にするブール値です。デフォルト値は `false` です。Activity Map のデータ収集を有効にする場合は、この値を `true` に設定します。

```js
s.trackInlineStats = true;
```
