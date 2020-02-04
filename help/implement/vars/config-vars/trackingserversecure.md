---
title: trackingServerSecure
description: HTTPSページで送信される場所のイメージ要求を決定します。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServerSecure

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。 この変 `trackingServerSecure` 数は、イメージリクエストがHTTPS経由で送信される場所を決定します。 また、訪問者のcookieが保存される場所も決定します。 この変数が正しく定義されていない場合は、実装でデータが失われる可能性があります。

> [!IMPORTANT] この値を変更すると、AppMeasurementが別の場所でcookieを探します。 個別訪問者数は、訪問者のcookieが新しい場所に設定されているので、レポートで一時的に急増する可能性があります。

## Adobe Experience Platform LaunchのSSLトラッキングサーバー

[!UICONTROL 「SSL Tracking Server] 」は、Adobe Analytics拡張機能を設定する際に  、一般アコーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「 [!UICONTROL General] 」アコーディオンを展開すると、「 [!UICONTROL SSL Tracking Server] 」フィールドが表示されます。

このフィールドを空白のままにすると、変数内の値がデフォルトになり `trackingServer` ます。

## AppMeasurementのs.trackingServerSecureおよびカスタムコードエディターの起動

変数 `s.trackingServerSecure` は、イメージ要求を送信する場所を含む文字列です。 ほとんどの場合、サイトのサブドメインです。 ブラウザーの最新のプライバシープラクティスは、一般にサードパーティcookieを信頼性の低いものにします。 この変数が空白の場合、変数内の値が使用され `s.trackingServer` ます。

この変数の値は、ほとんど常に、などのファーストパーティドメインです `data.example.com`。 ファー [ストパーティcookieのプロセスについて詳しくは、コアサービスユーザーガイドのExperience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) (Experience Cloud)で「ファーストパーティcookie」を参照してください。

ファーストパーティcookieの実装を最初に設定するユーザーも、使用するドメインとサブドメインを定義します。 次に例を示します。

```js
s.trackingServerSecure = "data.example.com";
```

CNAMEレコードは通常、のサブドメインを指しま `ssl.d1.sc.omtrdc.net`す。
