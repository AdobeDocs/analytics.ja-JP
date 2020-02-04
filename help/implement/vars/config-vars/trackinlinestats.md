---
title: trackInlineStats
description: 実装でActivity mapを有効または無効にします。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackInlineStats

アクティビティマップは、訪問者がクリックした場所とクリックした内容に関するデータを収集する、Adobe Analyticsの機能です。 このデータは、Analyticsレポートで表示することも、ブラウザー拡張機能オーバーレイを使用して表示することもできます。 Activity map機能を使用する場合は、この変数を有効にします。

有効な場合、AppMeasurementはリンクに関する情報を収集し、そのデータを次のイメージリクエストに送信します。 各クリックからの情報は、cookieラベルに保存されま `s_sq`す。

## Adobe Experience Platform LaunchでのClickmapの有効化

[!UICONTROL 「Clickmapを有効にする] 」は、Adobe Analytics拡張の設定時に、「リ [!UICONTROL ンクトラッキング] 」アコーディオンの下にあるチェックボックスです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「リンクトラッ [!UICONTROL キング] 」アコーディオンを展開すると、「Clickmapを有効にする」チェ [!UICONTROL ックボックスが表示されます] 。

チェックボックスをクリックして、Activity mapの追跡を有効にします。

## AppMeasurementおよび起動のカスタムコードエディターのs.trackInlineStats

は、Activity `s.trackInlineStats` マップの追跡を有効または無効にするブール値です。 Its default value is `false`. Activity mapのデータ収集を有 `true` 効にする場合は、この値をに設定します。

```js
s.trackInlineStats = true;
```
