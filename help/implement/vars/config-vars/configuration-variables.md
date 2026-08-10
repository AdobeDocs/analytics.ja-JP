---
title: 設定変数
description: 設定変数を使用して、データの収集方法を決定します。
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 383
ht-degree: 19%

---

# 設定変数の概要

設定変数は、データが取得され、レポートで処理される方法を制御します。 通常、ディメンションや指標の値は含まれません。

## 設定変数の設定

Web SDK拡張機能またはAnalytics拡張機能を使用する実装では、通常、拡張機能の設定に設定変数があります。

1. Adobe IDの資格情報を使用して[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection)にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブをクリックし、拡張機能の下の「[!UICONTROL 設定]」をクリックします。

`AppMeasurement.js` を使用した JavaScript 実装では、通常、設定変数は JS ファイルの先頭に設定されます。

>[!IMPORTANT]
>
>トラッキングメソッド （[`t()`](../functions/t-method.md)または[`tl()`](../functions/tl-method.md)）を呼び出す前に、すべての設定変数が設定されていることを確認してください。 [`doPlugins()`](../functions/doplugins.md) 関数内で設定変数を設定しないでください。

## 廃止された設定変数

次の設定変数は廃止されました。 レガシー実装で発生した場合は、参考用にここに文書化されています。

* **`account`**: データの送信先のレポートスイートを決定しました。 レポートスイートは、トラッキングオブジェクトのインスタンス化（[`s_gi()`](../functions/s-gi.md) メソッド）を通じて処理されるようになりました。 トラッキングオブジェクトのインスタンス化後にレポートスイートを変更する必要がある場合は、[`s.sa()`](../functions/sa-method.md) メソッドを使用します。
* **`cookieDomain`**: AppMeasurementがCookieを設定するドメインを決定しました。 現在のバージョンのAppMeasurementでは、適切なCookie ドメインが自動的に検出されるため、この変数は廃止されます。
* **`cookieDomainPeriods`**: ドメインに複数の期間が含まれている場合に、AppMeasurementがCookieの保存場所を決定するのに役立ちました。 現在のバージョンのAppMeasurementでは、正しいドメインが自動的に検出されるため、この変数は廃止されます。
* **`fpCookieDomainPeriods`**: 1st パーティドメインのサフィックスに余分な期間（`example.co.uk`など）が含まれている場合に、Cookieを正しい場所に設定するために使用される、`cookieDomainPeriods`と同等の1st パーティドメイン。 現在のバージョンのAppMeasurementでは、正しいドメインが自動的に検出されるため、この変数は廃止されます。
* **`trackingServer`**: HTTP経由でAdobeにデータを送信するために使用するドメインを指定しました。 HTTPSよりも安全なデータ収集を優先するため、この機能は推奨されません。 代わりに、[`trackingServerSecure`](trackingserversecure.md) を使用してください。
* **`trackInlineStats`**: [Activity Map](/help/analyze/activity-map/overview.md)の以前のバージョンを有効または無効にしました。
* **`visitorMigrationKey`**：訪問者をサードパーティ Cookieからファーストパーティ Cookieに移行するために使用されるキーが含まれています。 最新のライブラリが1st パーティフォールバッククッキー（`fid`）を設定し、IDに訪問者ID サービスを利用しているため、この機能は廃止されました。
* **`visitorMigrationServer`**: サードパーティからファーストパーティ Cookieへの移行中に使用するサーバーを指定しました。
* **`visitorMigrationServerSecure`**: `visitorMigrationServer`と同等のHTTPSです。
* **`visitorNameSpace`**: サードパーティ Cookie ドメインの決定に役立ちました。 訪問者ID サービスを使用しない実装に[`trackingServerSecure`](trackingserversecure.md)変数を使用することを優先して廃止されました。
