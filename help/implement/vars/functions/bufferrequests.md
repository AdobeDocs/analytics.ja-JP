---
title: bufferRequests
description: ページを直ちにアンロードするブラウザーに対するリンクトラッキングリクエストのキャプチャの信頼性を高めます。
feature: Variables
source-git-commit: d97e559e203182368bcbb62f51ef2c3e3bd025d3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 6%

---

# bufferRequests

The `bufferRequests()` メソッドを使用すると、イメージリクエストをAdobeに送信する代わりに、現在のページのイメージリクエストをキャッシュできます。 このメソッドをトリガーするのは、ブラウザーがをサポートしていないシナリオで役立ちます [`navigator.sendBeacon()`](https://developer.mozilla.org/ja-JP/docs/Web/API/Navigator/sendBeacon) またはを使用すると、ページのアンロード時にイメージリクエストがキャンセルされます。 Safari など、WebKit ブラウザーの多くのバージョンでは、一般的に、リンクをクリックしたときにイメージリクエストが停止する動作が示されます。 The `bufferRequests()` メソッドは、AppMeasurementv2.25.0以降のすべてのバージョンで使用できます。

を呼び出すとき [`t()`](t-method.md) または [`tl()`](tl-method.md) 同じブラウザーセッションの後続のページで、 `bufferRequests()` がそのページでまだ呼び出されていない場合、バッファされたすべてのリクエストがそのページのイメージリクエストに加えて送信されます。 バッファされたリクエストは正しい順序で送信され、現在のページのイメージリクエストが最後に送信されます。

>[!TIP]
>
>バッファーされたリクエストのタイムスタンプは、データが送信されるページと共有されます。 バッファリクエストが記録される正確な時間を秒単位で絞り込む場合は、 [`timestamp`](../page-vars/timestamp.md) ページ変数を使用して、要求をバッファリングする必要があります。 この変数を使用する場合は、 [タイムスタンプオプション](/help/technotes/timestamps-optional.md) が有効 — 有効でない場合、すべてのタイムスタンプ付きヒットが永久的に失われます。

## 制限事項

を呼び出す際に、 `bufferRequests()` メソッドの場合は、次の制限事項に注意してください。 この方法では [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)には、次の同じ制限の多くが当てはまります。

* 宛先リンクは、同じドメインとサブドメインに存在する必要があります。 バッファーされたリクエストは、ドメイン間またはサブドメイン間では機能しません。両方のドメインが同じAdobe Analytics実装を持っている場合でも同様です。 また、この制限は、バッファーされたリクエストを使用して出口リンクを追跡できないことを意味します。
* リンク先は、現在のページと同じプロトコルを使用する必要があります。 バッファーされたリクエストは、HTTP と HTTPS の間で送信できません。
* バッファーされたリクエストは、 `t()` または `tl()` 電話なしで `bufferRequests()` 最初に、またはブラウザーまたはタブが閉じられるまで。 データをAdobeに送信する前にブラウザセッションが終了すると、未送信のバッファリクエストは永久的に失われます。
* ブラウザーが [Web ストレージ API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) または [JSON API](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)を指定した場合、警告がブラウザーコンソールに出力され、AppMeasurementは、 `t()` メソッド。

## Web SDK でバッファーされたリクエスト

現在、Web SDK は、リクエストをバッファリングする機能を提供していません。

## Adobe Analytics拡張機能を使用したバッファーされたリクエスト

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementと Analytics 拡張機能のカスタムコードエディターの s.bufferRequests()

を呼び出します。 `bufferRequests()` 呼び出し前のメソッド `t()` または `tl()`. 条件 `bufferRequests()` が呼び出されると、以降のトラッキングコールは、セッションデータ収集サーバーに送信されるのではなく、Adobeストレージに書き込まれます。

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

<!-- TODO: insert a link to this page in AppMeasurement release notes, and also add content to Analytics release notes -->