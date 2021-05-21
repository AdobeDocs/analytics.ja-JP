---
title: trackInlineStats
description: 実装で Activity Map を有効または無効にします。
keywords: Activity Map を無効にする
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '192'
ht-degree: 100%

---

# trackInlineStats

Activity Map は、訪問者がクリックした場所とクリックした内容に関するデータを収集する、Adobe Analytics の機能です。このデータは、Analytics レポートで表示することも、ブラウザー拡張機能オーバーレイを使用して表示することもできます。Activity Map 機能を使用する場合は、この変数を有効にします。

有効な場合、AppMeasurement はリンクに関する情報を収集し、そのデータを次のイメージリクエストに送信します。各クリックからの情報は、「`s_sq`」Cookie に保存されます。

## Adobe Experience Platform Launch の「Clickmap の有効化」

「[!UICONTROL Clickmap の有効化]」は、Adobe Analytics 拡張機能の設定時に「[!UICONTROL リンクトラッキング]」アコーディオンの下にあるチェックボックスです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. 「[!UICONTROL 拡張機能]」タブに移動し、「Adobe Analytics」の下にある「[!UICONTROL 設定]」ボタンをクリックします。
4. 「[!UICONTROL リンクトラッキング]」アコーディオンを展開すると、「[!UICONTROL Clickmap の有効化]」チェックボックスが表示されます。

チェックボックスをクリックして、Activity Map のトラッキングを有効にします。

## AppMeasurement および Launch カスタムコードエディターの s.trackInlineStats

`s.trackInlineStats`は、Activity Map のトラッキングを有効または無効にするブール値です。デフォルト値は `false` です。Activity Map のデータ収集を有効にする場合は、この値を `true` に設定します。

```js
s.trackInlineStats = true;
```
