---
title: bufferRequests
description: ページを直ちにアンロードするブラウザーに対するリンクトラッキングリクエストのキャプチャの信頼性を高めます。
feature: Variables
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# bufferRequests

`bufferRequests()` メソッドを使用すると、イメージリクエストをAdobeに送信する代わりに、現在のページでキャッシュできます。 このメソッドのトリガーは、ブラウザーが [`navigator.sendBeacon()`](https://developer.mozilla.org/ja-JP/docs/Web/API/Navigator/sendBeacon) をサポートしていない場合や、ページの読み込み時に画像リクエストがキャンセルされる場合に便利です。 Safari などの多くのバージョンの WebKit ブラウザーは、リンクをクリックするとイメージリクエストを停止する動作を通常示します。 `bufferRequests()` の方法は、AppMeasurement v2.25.0 以降のすべてのバージョンで使用できます。

同じブラウザーセッション内の後続のページで [`t()`](t-method.md) または [`tl()`](tl-method.md) を呼び出し、そのページでまだ `bufferRequests()` が呼び出されていない場合、そのページのイメージリクエストに加えて、すべてのバッファーされたリクエストが送信されます。 バッファ・リクエストは正しい順序で送信されます。この順序では、現在のページのイメージ・リクエストが最後に送信されます。

>[!TIP]
>
>バッファーされた要求のタイムスタンプは、データが送信されたページと共有されます。 バッファされた要求が記録される正確な秒数でより正確な情報が必要な場合は、要求をバッファする前に [`timestamp`](../page-vars/timestamp.md) ページ変数を設定できます。 この変数を使用する場合は、「タイムスタンプ [ オプション ](/help/technotes/timestamps-optional.md) が有効になっていることを確認します。有効になっていなければ、タイムスタンプが付いたすべてのヒットが完全に失われます。

## 制限事項

`bufferRequests()` メソッドを呼び出す場合、次の制限事項に注意してください。 このメソッドでは [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) を使用するので、次のように多くの同じ制限が適用されます。

* 宛先リンクは、同じドメインとサブドメインに存在する必要があります。 バッファーされたリクエストは、ドメインとサブドメインの両方が同じAdobe Analytics実装を持っている場合でも、両方のドメインで機能しません。 また、この制限により、バッファーされたリクエストを使用して離脱リンクを追跡することはできません。
* 宛先リンクは、現在のページと同じプロトコルを使用する必要があります。 HTTP と HTTPS の間でバッファーされた要求を送信することはできません。
* バッファ・リクエストは、最初に `bufferRequests()` を呼び出さずに `t()` または `tl()` を呼び出すか、ブラウザまたはタブが閉じられるまで保存されます。 Adobeに送信する前にブラウザ・セッションが終了すると、未送信のバッファ・リクエストは永久に失われます。
* ブラウザーが [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) または [JSON API](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON) をサポートしていない場合、警告がブラウザーコンソールに出力され、AppMeasurementは `t()` メソッドを使用してイメージリクエストを直ちに送信しようとします。

## Web SDK のバッファー済みリクエスト

Web SDK は現在、リクエストをバッファーする機能を提供していません。

## Adobe Analytics拡張機能を使用したバッファーされたリクエスト

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの s.bufferRequests （）と Analytics 拡張機能のカスタムコードエディター

`t()` または `tl()` を呼び出す前に、`bufferRequests()` メソッドを呼び出します。 `bufferRequests()` が呼び出されると、後続のトラッキングコールは、Adobeデータ収集サーバーに送信されるのではなく、セッションストレージに書き込まれます。

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
