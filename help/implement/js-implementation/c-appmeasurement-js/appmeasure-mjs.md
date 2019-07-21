---
description: JavaScript 版 AppMeasurement は s_code.js と同じ機能を提供する新しいライブラリですが、モバイルサイトとデスクトップサイトのどちらで使用してもより軽量で高速です。
keywords: appMeasurement;Analyticsの導入;javascript;javascript for javascript;初期化;AppMeasurementインスタンスを取得します。clear vars;clearvars;appMeasurementユーティリティ;AppMeasurementインスタンス、AppMeasurementの利点
seo-description: JavaScript 版 AppMeasurement は s_code.js と同じ機能を提供する新しいライブラリですが、モバイルサイトとデスクトップサイトのどちらで使用してもより軽量で高速です。
seo-title: JavaScript 版 AppMeasurement について
solution: Analytics
subtopic: JavaScript AppMeasurement
title: JavaScript 版 AppMeasurement について
topic: 開発者と導入
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# JavaScript 版 AppMeasurement について

[!DNL AppMeasurement]JavaScript 版 は s_code.js と同じ機能を提供する新しいライブラリですが、モバイルサイトとデスクトップサイトのどちらで使用してもより軽量で高速です。

## 移行の前に知っておくべきこと {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* 一部のプラグインはサポートされなくなりました。[AppMeasurementプラグインのサポート](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A)を参照してください。
* The library does not support dynamic account selection ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* The library and page code can be deployed inside the `<head>` tag.
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. Surveyモジュールはサポートされません。
* 既存のページコードは新しいバージョンと互換性があります。
* このライブラリは、クエリパラメーターの取得、cookie の読み取り／書き込み、高度なリンクトラッキングの実行のためのネイティブユーティリティを含みます。

## よくある質問 {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## 初期化プロセス {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

When `s_gi` is called, if an [!DNL AppMeasurement] instance does not exist for the specified `s_account`, a new instance is created. それ以外の場合は、既存のインスタンスが返されます。この機能により、同じアカウントに対して重複オブジェクトを作成しないようにすることができます。

## AppMeasurement インスタンスの取得 {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## ユーティリティ {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## 変数のクリア {#section_597C411E7EDB42BC9A6A0508C9D57147}

新しい `clearVars` メソッドを使用して、インスタンスオブジェクトから以下の値をクリアできます。

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

以下に例を示します。

```js
s.clearVars()
```

## 利点 {#section_091E5A28E89E438E8A54A95F55165743}

* H.25 コードと比較して 3 倍 ～ 7 倍も高速。
* わずか 21K の非圧縮コード、8K の gzip 圧縮コード（H.25 コードでは、33K もの非圧縮コード、13K の gzip 圧縮コード）。
* 一般的なプラグインの多くをネイティブサポート。
* モバイルサイトで使用できるほど軽量かつ高速で、フルデスクトップ Web で使用できるほど堅牢。1 つのライブラリを Web 環境全体で活用できます。

