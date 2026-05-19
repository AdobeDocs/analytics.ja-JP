---
title: 実装 FAQ
description: 実装に関するよくある質問と、詳細情報へのリンクです。
feature: Implementation Basics
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/Hm9pIJE9P3jEljJAgB69k2M9-fTa9G0wsCjfvN4xH3E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c77ba355-6681-41fe-b719-563d3f507fdbid: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 96%

---

# Analytics の実装に関する FAQ

実装に関するよくある質問と、詳細情報へのリンクです。

## Experience Cloud 訪問者 ID と Analytics 訪問者 ID の違いは何ですか。

ID サービスは、CX Enterpriseの他のソリューション間で共有できる、一意の永続的なIDを割り当てます。 Analytics 訪問者 ID は、Analytics でのみ使用されます。 実装に Experience Cloud 訪問者 ID サービスを使用することをお勧めします。

## ハートビートビデオトラッキングを実装する方法を教えてください。

[Adobe Analytics でのオーディオおよびビデオの測定](https://experienceleague.adobe.com/ja/docs/media-analytics/using/media-overview)を参照してください。

## アドビのサービスを中断すると、パフォーマンスに影響を与える可能性はありますか。

いいえ。 JavaScript ファイルは、アドビのサーバーでホストされていないでため、アドビの停止状態が AppMeasurement ライブラリに影響することはありません。 Adobe Experience Platform のタグを使用する場合、JavaScript ファイルは Akamai または組織が決定したサーバーでホストされます。

## ブラウザーからアドビのサーバーにデータを送信することによってパフォーマンスが低下することはありますか。

AppMeasurement は、HTML ページ内にイメージオブジェクトを作成し、ブラウザーは、Adobe データ収集サーバーからイメージオブジェクトをリクエストします。 データ収集サーバーが低速になったり応答しなくなった場合、そのリクエストを処理するスレッドは、イメージが返されるかタイムアウトが発生するまで、遅延します。 ブラウザーはイメージを複数のスレッドで処理するので、アドビの停止状態はページ読み込み時間にわずかな影響しか与えず、1 つのスレッドが停止していても、他のスレッドは機能し続けます。

## Analytics 実装を無効にする、または削除する方法を教えてください。

組織では、契約の有効期限切れやサーバーコールの数の減少が原因で実装を削除したい場合があります。

* **Adobe Experience Platform データ収集を使用した実装**：「[!UICONTROL 拡張機能]」タブで該当する Adobe Analytics、Web SDK または Mobile SDK 拡張機能を無効にするかアンインストールして、公開します。
* **従来の AppMeasurement の実装**：`s_code.js` ファイルの内容全体を次のコード行に置き換えます。

```js
var s = new Object();
```

>[!WARNING]
>
>以下は禁止されています。
>
>* レポートスイートを無効な値に変更すること（アドビのサーバーに不要な読み込みが発生する）
>* `s_code.js` ファイルを完全に削除すること（各ページのファイルへの参照をすべて削除する場合を除く ）
>* `trackingServer` 変数をアドビ以外を参照するように変更すること。 AppMeasurement は引き続きイメージリクエストを送信し、404 エラーを返します。

## コードアナライザを通じて AppMeasurement を実行したところ、潜在的なセキュリティリスクとして `Math.random()` の使用にフラグが付きました。 `Math.random()` は機密データで使用されますか？

いいえ。 `Math.random()` を使用する数値は、機密データのマスク、送信、受信には使用されません。 アドビのデータ収集サーバーに送信されるデータは、基になる HTTPS 接続のセキュリティに依存します。<!-- AN-173590 -->

AppMeasurement は、次の 3 つの主要な領域で `Math.random()` を使用します。

* **サンプリング**：実装によっては、サイトへの訪問者のごく一部についてのみ収集される情報もあります。 `Math.random()` は、特定の訪問者がデータを送信する必要があるかどうかを判断するために使用されます。 ほとんどの実装では、サンプリングを使用しません。
* **フォールバック訪問者 ID**：訪問者 ID を Cookie から取得できない場合は、ランダムな訪問者 ID が生成されます。 AppMeasurement のこの部分では、`Math.random()` への 2 回の呼び出しを使用します。
* **キャッシュバスティング**：ブラウザーのキャッシュを防ぐために、画像リクエスト URL の末尾に乱数が追加されます。
