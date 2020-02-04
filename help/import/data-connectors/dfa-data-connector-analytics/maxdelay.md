---
title: maxDelay
description: AppMeasurementがDFAからの応答を待ってからイメージリクエストを送信するまでの最大時間を指定します。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# maxDelay

The `s.maxDelay` variable is used in the DFA data connector to determine the timeout period in contacting the DFA host. この変数に設定された指定された期間内にアドビがDFAのサーバーから応答を受け取らなかった場合、接続が切断され、データは通常どおり処理されます。 各ページでのDFAの応答時間が問題となる場合は、この変数を実装に含めます。 最適なタイムアウト期間を決定するには、この値を試すことをお勧めします。

この変数は、DFAデータコネクタを使用する実装でのみ使用されます。 DFAを使用した実装でも、この変数はオプションです。

## Adobe Experience Platformの起動の最大遅延

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.maxDelayとカスタムコードエディターの起動

変数 `s.maxDelay` は、AppMeasurementがDFAからの応答を待機するミリ秒数を表す整数です。 AppMeasurementがDFAからの応答を時間内に受信しない場合、イメージリクエストはDFAデータなしでアドビに送信されます。

```js
s.maxDelay = 750;
```

## プロパティ

* 待機時間を増加させるとより多くの DFA データが収集されますが、Analytics のヒットデータを失うリスクも高くなります。Losing Analytics hit data happens when the user navigates away from the page during the `s.maxDelay` period.
* 待機時間を減らすと、Analyticsのヒットデータを失うリスクは低くなりますが、ヒットデータと共に送信されるDFAデータの量は少なくなります。
* Losing DFA integration data happens when the `s.maxDelay` period does not accommodate enough time for the DFA host to respond.

> [!NOTE]アドビは DFA の応答時間を制御していません。最大遅延時間を妥当な期間に延長した後でも一貫した問題が発生する場合は、組織のDFAアカウント管理者に問い合わせてください。
