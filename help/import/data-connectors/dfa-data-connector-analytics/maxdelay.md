---
title: maxDelay
description: AppMeasurement がイメージリクエストを送信するまで　DFA からの応答を待機する最大の時間を指定します。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# maxDelay

`s.maxDelay` 変数は主に DFA 統合で使用され、DFA ホストと通信する際のタイムアウト時間を指定します。変数で設定された指定の時間内にアドビが DFA のサーバーから応答を受信しない場合、接続が切断されますが、データは通常どおりに処理されます。各ページで DFA の応答時間を使用する場合は、この変数を実装に含めてください。アドビでは、この値を試し、最適なタイムアウト時間を判断することをお勧めします。

この変数は、DFA データコネクタを使用する実装でのみ使用されます。DFA を使用している実装であっても、この変数はオプションです。

## Adobe Experience Platform Launch の最大遅延

Launch には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムのコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s.maxDelay

`s.maxDelay` 変数は、AppMeasurement が DFA からの応答を待機する時間（ミリ秒）を表す整数です。AppMeasurement が時間内に DFA からの応答を受信しない場合、イメージリクエストは DFA データなしでアドビへと送信されます。

```js
s.maxDelay = 750;
```

## プロパティ

* 待機時間を増やすと収集される DFA データも多くなりますが、Analytics のヒットデータを失うリスクも高くなります。`s.maxDelay` の期間中にユーザーがページから離脱すると、Analytics のヒットデータの損失が発生する可能性があります。
* 待機時間を減らすと Analytics のヒットデータを失うリスクは低くなりますが、ヒットデータと一緒に送信される DFA データの量も少なくなります。
* DFA統合データの損失は、`s.maxDelay` 期間が DFA ホストの応答に十分でない場合に発生します。

>[!NOTE]アドビは DFA の応答時間を制御していません。最大遅延期間を妥当な時間枠に増やした後でも整合性の問題が見られる場合は、貴社の DFA アカウント管理者にお問い合わせください。
