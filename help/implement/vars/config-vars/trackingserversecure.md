---
title: trackingServerSecure
description: HTTPS ページでイメージリクエストが送信される場所を決定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# trackingServerSecure

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。`trackingServerSecure` 変数は、イメージリクエストが HTTPS 経由で送信される場所を決定します。また、訪問者の Cookie が保存される場所も決定します。この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

>[!IMPORTANT] この値を変更すると、AppMeasurement が別の場所で Cookie を探します。訪問者の Cookie が新しい場所に設定されると、レポートで個別訪問者数が一時的に急増する可能性があります。

## Adobe Experience Platform Launch の「SSL トラッキングサーバー」

[!UICONTROL SSL Tracking Server] は、Adobe Analytics拡張を設定する際に、ア [!UICONTROL General] コーディオンの下にあるフィールドです。

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL General] ンを展開すると、フィールドが表示 [!UICONTROL SSL Tracking Server] されます。

このフィールドを空白のままにすると、[`trackingServer`](trackingserver.md) 変数の値がデフォルトになります。

## AppMeasurement および Launch カスタムコードエディターの s.trackingServerSecure

`s.trackingServerSecure` 変数は、イメージリクエストを送信する場所を含む文字列です。ほとんどの場合、これはサイトのサブドメインです。ブラウザーの最新のプライバシープラクティスによって、一般的なサードパーティ Cookie の信頼性が低下しています。この変数が空白の場合、`s.trackingServer` 変数の値が使用されます。

この変数の値は、ほとんど常に、`data.example.com` などのファーストパーティドメインです 。ファーストパーティ Cookie のプロセスについて詳しくは、『コアサービスユーザーガイド』の [Experience Cloud でのファーストパーティ Cookie](https://docs.adobe.com/content/help/ja-JP/core-services/interface/ec-cookies/cookies-first-party.html) を参照してください。

実装でファーストパーティ Cookie を初期設定するユーザーも、使用するドメインとサブドメインを定義します。次に例を示します。

```js
s.trackingServerSecure = "data.example.com";
```

CNAME レコードは通常、`ssl.d1.sc.omtrdc.net` のサブドメインを指します。
