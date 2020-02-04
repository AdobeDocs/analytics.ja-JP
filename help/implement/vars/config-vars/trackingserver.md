---
title: trackingServer
description: 送信する場所のイメージ要求を決定します。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServer

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。 この変 `trackingServer` 数は、イメージリクエストが送信される場所を決定します。 この変数が正しく定義されていない場合は、実装でデータが失われる可能性があります。

> [!IMPORTANT] この値を変更すると、AppMeasurementが別の場所でcookieを探します。 個別訪問者数は、訪問者のcookieが新しい場所に設定されているので、レポートで一時的に急増する可能性があります。

## Adobe Experience Platform Launchのトラッキングサーバー

Adobe Analytics拡張機能を設定する際の「一般」アコ [!UICONTROL ーディオンの下に] 、「トラッキングサーバー」と表示されるフィールドです。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 目的のプロパティをクリックします。
3. 「拡張」タブに移 [!UICONTROL 動し] 、「Adobe Analytics」の下にある「設 [!UICONTROL 定] 」ボタンをクリックします。
4. 「一般」アコー [!UICONTROL ディオンを展開すると] 、「トラッキングサーバー」 [!UICONTROL フィールドが表示されます] 。

このフィールドを空白のままにすると、デフォルトではになりま `[rsid].112.2o7.net`す。

## AppMeasurementのs.trackingServerとカスタムコードエディターの起動

変数 `s.trackingServer` は、データを送信する場所を含む文字列です。

> [!TIP] 一部の実装では、データがを指し示しま `2o7.net`す。 これは有効なデータ収集ドメインですが、地域データ収集は使用されません。 イメージリクエストの `2o7.net` 応答時間が若干長くなるように実装する。

## trackingServerの値の決定

この変数の値は、ファーストパーティCookieとサードパーティCookieのどちらを使用するかによって異なります。 導入時にファーストパーティcookieを使用することを強くお勧めします。

### ファーストパーティ cookie

ファーストパーティcookieの導入を使用する場合、組織内の任意のユーザーが既にファーストパーティcookieのプロセスを完了している可能性があります。 ファー [ストパーティcookieのプロセスについて詳しくは、コアサービスユーザーガイドのExperience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) (Experience Cloud)で「ファーストパーティcookie」を参照してください。

ファーストパーティcookieの実装を最初に設定するユーザーも、使用するドメインとサブドメインを定義します。 次に例を示します。

```js
s.trackingServer = "data.example.com";
```

通常、CNAMEレコードは既に設定済みで、をポイントしま `sc.omtrdc.net`す。 また、ドメ `2o7.net` インは有効なCNAMEの宛先でもあり、主に以前のバージョンのAdobe Analyticsで使用されます。

### サードパーティcookie

> [!TIP] 最新のブラウザーでプライバシーの慣行が増えると、サードパーティcookieの信頼性が低下します。 アドビでは、ファーストパーティcookieのワークフローに従うことをお勧めします。

サードパーティcookieの実装を使用する場合、の値はのサブ `trackingServer` ドメインになりま `sc.omtrdc.net`す。 次に例を示します。

```js
s.trackingServer = "example.sc.omtrdc.net";
```

組織に固有のサブドメインを選択します。Adobe Analyticsを使用する別の組織では採用されないサブドメインを選択します。 組織内のすべての実装で同じトラッキングサーバーを使用していることを確認します。 この情報は、ソリューションデザインドキュメントで保守する [と役に立ちます](../../prepare/solution-design.md)。
