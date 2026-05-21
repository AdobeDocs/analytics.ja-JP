---
title: bufferRequests
description: ページをすぐにアンロードするブラウザーに対して、リンクトラッキングリクエストをキャプチャする信頼性を向上させます。
feature: Appmeasurement Implementation
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
TQID: https://experienceleague.adobe.com/HJdo1hCpisjHdOaTi8OP2tWSP2yAftEqfkCNXycFcrM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 7%

---

# bufferRequests

`bufferRequests()` メソッドを使用すると、Adobeに画像リクエストを送信する代わりに、現在のページに画像リクエストをキャッシュできます。 このメソッドのトリガーは、ブラウザーが[`navigator.sendBeacon()`](https://developer.mozilla.org/ja-JP/docs/Web/API/Navigator/sendBeacon)をサポートしていない場合や、ページのアンロード時に画像要求をキャンセルする場合に便利です。 SafariなどのWebKit ブラウザーの多くのバージョンでは、一般的に、リンクをクリックすると画像リクエストを停止する動作が示されます。 `bufferRequests()` メソッドは、AppMeasurement v2.25.0以降のすべてのバージョンで使用できます。

同じブラウザーセッションの後続ページで[`t()`](t-method.md)または[`tl()`](tl-method.md)を呼び出し、そのページで`bufferRequests()`がまだ呼び出されていない場合、そのページのイメージリクエストに加えてすべてのバッファリングされたリクエストが送信されます。 バッファリングされたリクエストは、現在のページの画像リクエストが最後に送信される正しい順序で送信されます。

>[!TIP]
>
>バッファリングされたリクエストのタイムスタンプは、データが送信されるページと共有されます。 バッファリングされたリクエストが正確に2秒間に記録されるより高い精度が必要な場合は、リクエストのバッファリングの前に[`timestamp`](../page-vars/timestamp.md) ページ変数を設定できます。 この変数を使用する場合は、[&#x200B; タイムスタンプオプション &#x200B;](/help/admin/tools/manage-rs/edit-settings/general/timestamp-configuration.md)が有効になっていることを確認してください。有効になっていない場合、すべてのタイムスタンプ付きヒットが完全に失われます。

## 制限事項

`bufferRequests()` メソッドを呼び出す場合は、次の制限事項に注意してください。 このメソッドは[`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)を使用するため、同じ制限の多くが適用されます。

* 宛先リンクは、同じドメインとサブドメインに存在する必要があります。 バッファリングされたリクエストは、同じAdobe Analytics実装を持っている場合でも、ドメインまたはサブドメイン間で機能しません。 この制限は、バッファリングされたリクエストを使用して終了リンクを追跡できないことを意味します。
* 宛先リンクは、現在のページと同じプロトコルを使用する必要があります。 HTTPとHTTPSの間でバッファリングされたリクエストを送信することはできません。
* バッファリングされた要求は、最初に`bufferRequests()`を呼び出さずに`t()`または`tl()`を呼び出すか、ブラウザーまたはタブが閉じられるまで保存されます。 そのデータをAdobeに送信する前にブラウザーセッションが終了すると、未送信のバッファリングされたリクエストは永続的に失われます。
* ブラウザーが[Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)または[JSON API](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)をサポートしていない場合、警告がブラウザーコンソールに出力され、AppMeasurementは`t()` メソッドを使用してイメージリクエストをすぐに送信しようとします。

## Web SDKでのバッファリングされたリクエスト

Web SDKは現在、リクエストをバッファリングする機能を提供していません。

## Adobe Analytics拡張機能を使用したバッファリング済みリクエスト

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。 AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs.bufferRequests （）とAnalytics拡張機能のカスタムコードエディター

`t()`または`tl()`を呼び出す前に、`bufferRequests()` メソッドを呼び出します。 `bufferRequests()`が呼び出されると、後続のトラッキング呼び出しは、Adobe データ収集サーバーに送信されるのではなく、セッションストレージに書き込まれます。

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```
