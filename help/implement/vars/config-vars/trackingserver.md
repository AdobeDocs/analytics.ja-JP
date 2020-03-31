---
title: trackingServer
description: イメージリクエストを送信する場所を決定します。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# trackingServer

アドビは、訪問者が生成したイメージリクエストを受け取ることで、サイト上のデータを収集します。`trackingServer` 変数は、イメージリクエストが送信される場所を決定します。この変数が正しく定義されていないと、実装でデータが失われる可能性があります。

> [!IMPORTANT] この値を変更すると、AppMeasurement が別の場所で Cookie を探します。訪問者の Cookie が新しい場所に設定されると、レポートで個別訪問者数が一時的に急増する可能性があります。

## Adobe Experience Platform Launch の「トラッキングサーバー」

Tracking Server is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. Adobe ID の資格情報を使用して [launch.adobe.com](https://launch.adobe.com) にログインします。
2. 目的のプロパティをクリックします。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. アコーディオ [!UICONTROL General] ンを展開すると、フィールドが表示 [!UICONTROL Tracking Server] されます。

このフィールドを空白のままにすると、デフォルトでは `[rsid].112.2o7.net` になります。

## AppMeasurement および Launch カスタムコードエディターの s.trackingServer

`s.trackingServer` 変数は、データを送信する場所を含む文字列です。

> [!TIP] 一部の実装では、データが `2o7.net` を指し示します。これは有効なデータ収集ドメインですが、地域データ収集は使用されません。`2o7.net` を使用して実装すると、イメージリクエストの応答時間が若干長くなります。

## trackingServer の値の決定

この変数の値は、ファーストパーティ Cookie とサードパーティ Cookie のどちらを使用するかによって異なります。実装にファーストパーティ Cookie を使用することを強くお勧めします。

### ファーストパーティ Cookie

ファーストパーティ Cookie の実装を使用する場合、組織内の任意のユーザーが既にファーストパーティ Cookie のプロセスを完了している可能性があります。ファーストパーティ Cookie のプロセスについて詳しくは、『コアサービスユーザーガイド』の [Experience Cloud でのファーストパーティ Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) を参照してください。

実装でファーストパーティ Cookie を初期設定するユーザーも、使用するドメインとサブドメインを定義します。次に例を示します。

```js
s.trackingServer = "data.example.com";
```

通常、CNAME レコードは既に設定済みで、`sc.omtrdc.net` をポイントします。また、`2o7.net` ドメインは有効な CNAME の宛先でもあり、主に以前のバージョンの Adobe Analytics で使用されます。

### サードパーティ Cookie

> [!TIP] 最新のブラウザーではプライバシー保護が強化されており、サードパーティ Cookie の信頼性が低下しています。ファーストパーティ Cookie のワークフローに従うことをお勧めします。

サードパーティ Cookie の実装を使用する場合、`trackingServer` の値は `sc.omtrdc.net` のサブドメインになります。次に例を示します。

```js
s.trackingServer = "example.sc.omtrdc.net";
```

Adobe Analytics を使用する別の組織では採用されないような、組織に固有のサブドメインを選択します。組織内のすべての実装で同じトラッキングサーバーを使用していることを確認します。[ソリューション設計ドキュメント](../../prepare/solution-design.md)でこの情報を維持すると役立つ場合があります。

> [!NOTE] より深いサブドメインは使用しないでくださ `example.sc.omtrdc.net`い。 例えば、は有効 `custom.example.sc.omtrdc.net` なトラッキングサーバーではありません。
