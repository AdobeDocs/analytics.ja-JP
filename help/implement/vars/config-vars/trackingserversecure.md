---
title: trackingServerSecure
description: HTTPSページで送信される場所のイメージ要求を決定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# trackingServerSecure

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。 この変 `trackingServerSecure` 数は、イメージリクエストがHTTPS経由で送信される場所を決定します。 また、訪問者のCookieが保存される場所も決定します。 この変数が正しく定義されていない場合は、実装でデータが失われる可能性があります。

> [!IMPORTANT] この値を変更すると、AppMeasurementで別の場所のCookieが検索されます。 個別訪問者数は、訪問者のcookieが新しい場所に設定されるので、レポートで一時的に急増する可能性があります。

## Adobe Experience Platform LaunchのSSL Tracking Server

[!UICONTROL SSL Tracking Server] は、Adobe Analytics拡張を設定する際に、ア [!UICONTROL General] コーディオンの下にあるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. タブに移動し、 [!UICONTROL Extensions] Adobe Analyticsの下のボタ [!UICONTROL Configure] ンをクリックします。
4. アコーディオ [!UICONTROL General] ンを展開すると、フィールドが表示 [!UICONTROL SSL Tracking Server] されます。

このフィールドを空白のままにすると、変数の値がデフォルト値になり [`trackingServer`](trackingserver.md) ます。

## AppMeasurementのs.trackingServerSecureとカスタムコードエディターの起動

変数 `s.trackingServerSecure` は、イメージ要求を送信する場所を含む文字列です。 ほとんど常に、サイトのサブドメインです。 ブラウザーの最新のプライバシープラクティスは、一般にサードパーティcookieを信頼性の低いものにします。 この変数が空白の場合、変数の値が使用され `s.trackingServer` ます。

この変数の値は、ほとんど常に、などのファーストパーティドメインです `data.example.com`。 ファー [ストパーティcookieのプロセスについて詳しくは、コアサービスユーザーガイドのExperience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) (Experience Cloud)で「ファーストパーティcookie」を参照してください。

ファーストパーティcookieの実装を最初に設定する個人も、使用するドメインとサブドメインを定義します。 次に例を示します。

```js
s.trackingServerSecure = "data.example.com";
```

CNAMEレコードは通常、のサブドメインを指しま `ssl.d1.sc.omtrdc.net`す。
